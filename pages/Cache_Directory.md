As of Principia 2025.04.05, the game now has a separate directory for storing temporary cache files that were previously stored in the [[User Data Directory]].

## Location for each platform
- **Windows**: `%LOCALAPPDATA%\Principia`
- **Linux**, **Haiku OS**, **macOS**: `$XDG_CACHE_DIR` (default `~/.cache/principia/`)
- **Android**: Scoped app cache directory
- Portable: `cache`

## Cache files
- **`fl.cache`**: Cached data for the main menu featured levels list.
- **`fonts.cache`** & **`models.cache`**: Cache files for fonts and models respectively to make the game load faster. They will be regenerated on next startup if deleted.
- **`cache/`**: Level cache. Temporary Lua files for editing in an external editor get saved here.
- **`lvl/db/`**: Directory where levels played from a community site are temporarily stored.
- **`pkg/db/`**: Directory where packages played from a community site are temporarily stored.

## Old cache in the user data directory
Prior to Principia 2025.04.05, the abovementioned cache files used to be saved in the user data directory. You can safely delete these files, and they will not reappear.
