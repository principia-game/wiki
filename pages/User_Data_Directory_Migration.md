(This page is a draft until the next release.)

In Principia 2026.XX.XX, the user data location was changed on Windows and Linux, and the directory structure was also changed. The game will try to migrate data automatically on first startup, but will leave behind anything that is not directly used by the game for the user to manually clean up if so desired.

## Location of user data directory

- Windows:
	- Old: `C:\Users\[username]\Principia`
	- New: `%APPDATA%\Principia` (`C:\Users\[username]\AppData\Roaming\Principia`)
- Linux:
	- Old: `~/.principia`
	- New: `$XDG_DATA_DIR/principia` (default: `~/.local/share/principia`)

Other platforms and portable installations retain the same location, but will still migrate the user data directory to the new structure in-place.

## Migration process
Upon starting the game it will check whether the user data should be migrated. The migration will happen under the following conditions:

- If oldpath != newpath (Windows and Linux): If the new directory location does not exist and there is something at the old directory location
- If oldpath == newpath (Android and portable installations): If the new `levels/` directory does not exist

The old directory is renamed to `Principia_old` and the new directory is created in order to move stuff over.

The following files are moved over at the root:

- `c` (renamed to `cookie_jar`)
- `community_host.txt` (not created by default)
- `data.bin`
- `run.log`
- `settings.ini`

The following are moved to the new `levels/` directory:

- `lvl/local/.autosave` (autosave level)
- `lvl/local/*.plvl` (levels)
- `lvl/local/*.pobj` (multi-select objects)
- `lvl/local/*.psol` (puzzle solutions)

The following are moved to the new `saves/` directory:

- `sav/*.psav` (save states)

The migration process will never delete any files remaining in the old directory as a safety precaution. If you want to clean it up you can do so manually, by going into the old directory which is now named `Principia_old` or similar.

If something went wrong during the migration process and you notice missing data, you can go into it and manually move it to the new location. Otherwise anything else remaining is most likely going to be old cache files you can safely delete (see [[Cache Directory]]), or files you have manually put into the directory.
