Principia uses a directory to store settings and levels. Sometimes you would want to access this to manage and backup your local levels, or to check the game logs.

## Location for each platform
- **Windows**: `C:\Users\[username]\Principia\`
- **Linux**, **Haiku OS**, **macOS**: `~/.principia/`
- **Android**:
    - **1.5.1 and prior**: `/sdcard/Principia/`
    - **1.5.2+**: `/storage/emulated/0/Android/data/com.bithack.principia/files/` (see [[Accessing Android Data Directory]])

The user data can be stored portably on desktop platforms if the file `portable.txt` is present next to the Principia executable. In this case the user data will be stored in a folder called `userdata` next to the executable.

## User data files
- **`community_host.txt`**: File for overriding the community domain used by the game. Not created by default, if file is absent the default (`principia-web.se`) will be used.
- **`c`**: cURL cookie file. ***NOTE:* Do not share this with anyone, as this will allow them to grab your principia-web login token!**
- **`data.bin`**: Contains miscellaneous game data such as package completion and highscore tracking.
- **`fl.cache`**: Cached data for the main menu featured levels list.
- **`fonts.cache`** & **`models.cache`**: Cache files for fonts and models respectively to make the game load faster. They will be regenerated on next startup if deleted.
- **`run.log`**: Log file for the latest session of the game.
- **`settings.ini`**: INI text file with game settings.
- **`cache/`**: Level cache. Temporary Lua files for editing in an external editor get saved here.
- **`lvl/`**: The place where levels are saved.
- **`pkg/`**: The place where packages are saved.
- **`sav/`**: Saved games that can be continued from the main menu.

### Level namespaces
For `cache/`, `lvl/` and `pkg/`, they are further split into "namespaces".

- **`db`**: Community site levels gets downloaded locally to this namespace before they are played.
- **`local`**: **This is where you find your locally saved levels!**
- **`main`**: Primarily for built-in levels (e.g. the built-in puzzle package), is usually always empty in the user data folder.
