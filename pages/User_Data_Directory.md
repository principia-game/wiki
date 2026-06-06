Principia uses a directory to store settings and levels. Sometimes you would want to access this to manage and backup your local levels, or to check the game logs.

## User data migration
In Principia 2026.06.06, the user data location was changed on Windows and Linux, and the directory structure was also changed. The game will try to migrate data automatically on first startup, but will leave behind anything not directly used by the game. For more information about this migration see [[User Data Directory Migration]].

## Location for each platform
- **Windows**: `%APPDATA%\Principia` (`C:\Users\[username]\AppData\Roaming\Principia`)
- **Linux**: `$XDG_DATA_DIR/principia` (default: `~/.local/share/principia`)
- **Haiku OS**: Same as Linux
- **macOS**: Unknown
- **Android**: `/storage/emulated/0/Android/data/com.bithack.principia/files/` (see [[Accessing Android Data Directory]])

The user data can be stored portably on desktop platforms if the file `portable.txt` is present next to the Principia executable. In this case the user data will be stored in a folder called `userdata` next to the executable.

## User data files
- **`community_host.txt`**: File for overriding the community domain used by the game.
    - Not created by default, if file is absent the default (`principia-web.se`) will be used.
- **`cookie_jar`**: cURL cookie file.
    - ***NOTE:* Do not share this with anyone, as this will allow them to grab your principia-web login token!**
- **`data.bin`**: Contains miscellaneous game data such as package completion and highscore tracking.
- **`run.log`**: Log file for the latest session of the game.
- **`settings.ini`**: INI text file with game settings.
- **`levels/`**: The place where levels (.plvl), multi-select objects (.pobj) and puzzle solutions (.psol) are stored.
- **`saves/`**: Saved games that can be continued from the main menu.

Prior to Principia 2025.04.05, cache files used to be saved in the user data directory. If your user data directory predates that version you likely have more files. See [[Cache Directory]] for a full list of files which can be safely deleted.
