This page contains the changelog for Principia.

For versions prior to the source code release, please see [[Old Changelog]].

[toc]

## 202X.XX.XX (upcoming release)
- New directory structure for user data
- Location of user data has been moved on some platforms:
  - Windows: Now in `%APPDATA%\Principia` instead of `C:\Users\<User>\Principia`
  - Linux: Now in `~/.local/share/principia` (or $XDG_DATA_HOME) instead of `~/.principia`
- Fix navigation bar obscuring the game on Android 15
- Fix crash when pressing F11 key on Android
- Fix username being shown in the topleft even if you are not actually logged in
- Fix game running slowly after logging in on desktop
- Set `SDL_HINT_APP_NAME` (used for e.g. Pipewire)
- Fix scaling of large ore blocks
- Improve the appearance of world borders
- Switch from GLEW to GLAD
- Web version is now pretty usable (but still experimental)

## 2025.04.05
**[News article](https://principia-web.se/news/19)** - **[Release](https://github.com/Bithack/principia/releases/tag/2025.04.05)**

- Reintroduce puzzles as a level type that can be created in the sandbox!
- The Level Manager object now works again!
- Rework the play menu in the main menu
- Optimise initial model loading on Android
- Move some unimportant files that the game saves into a new cache location
- Increase maximum Max value of Condenser to 32
- Increase maximum Weight multiplier to 2.5
- Increase chunk render limit (means less likelihood of seeing chunk gaps)
- Hopefully make GTK dialogs less likely to appear under the main window
- Make window no longer resizable by default (can be enabled again in settings)
- **Bugfixes**:
  - Fix RC widget screen breaking on resize
  - Fix various other GUI elements not adjusting to window resize
  - Fix crash when reloading graphics with rubber objects in a level
  - Fix crash when deleting a selected cable object
  - Fix crash when destroying a dead robot's bomb
  - Fix textured pixel not copying properties when using copying command
  - Fix not being able to open older levels in the sandbox
  - Fix Sqrt gate outputting NaN from out-of-bounds values
  - Fix Linear decay output value not being clamped
  - Fix a lot of other signaling objects lacking proper clamping
  - Fix plastic density being incorrectly applied on Android
- **Technical**:
  - Switch to Clang for Windows and Linux builds (fixes some graphical glitches, otherwise should be unnoticeable)
  - Merge data folders into one
  - Distinguish builds by Git commit rather than build time
  - Source tree cleanups, some things have moved or been renamed when building from source
  - Improvements for the experimental web port
  - Update dependency library versions

## 2024.07.12
**[News article](https://principia-web.se/news/16)** - **[Release](https://github.com/Bithack/principia/releases/tag/2024.07.12)**

- Fix VSync being disabled on Android (oh no)
- Fix not being able to play levels from the browser on Android
- Fix GLEW crashing the game when running the game with SDL2's Wayland video driver
- Fix orphaned prompts crashing the game when trying to close them
- Fix building Principia on Alpine-based Linux distributions

## 2024.06.28
**[News article](https://principia-web.se/news/15)** - **[Release](https://github.com/Bithack/principia/releases/tag/2024.06.28)**

- Merge sound data directories across platforms (makes sounds stereo on Android and fixes some missing sound files)
- Fix crash when attempting to save the state of a level with a LuaScript in it
- Revert to old colour picker on desktop (makes it easier to select Pixel alpha)
- Allow changing the community site domain at runtime
- Fix issue when playing from different community hosts during same gameplay session
- Fix some (not all) issues when window is resized
- Fix building with GCC 14
- Various code cleanups
- **Lua:**
  - Add `entity:set_fixed_rotation`
  - Add `entity:is_fixed_rotation`
  - Add `entity:apply_force`
- **Desktop:**
  - Allow storing user data portably on all desktop platforms (not just Windows)
  - Show an error message when a segfault crash happens
  - Allow toggling fullscreen with F11
- **Windows:**
  - Fix installer installing duplicate data-shared folder
  - Fix segfault on very old unsupported OpenGL versions (it gives a more friendly error instead)
- **Linux:**
  - Don't use Debian's broken SDL2 library for AppImage
  - Allow enabling OpenGL ES at compiletime (`USE_GLES`)
- **Android:**
  - Update SDL2 to latest 2.30.3
  - Switch to CMake
  - Fix crash when opening puzzle levels
  - Drop support for Android KitKat (5.0 Lollipop is now minimum)
- **macOS:**
  - Experimental port to macOS now available

## 2024.02.29
**[News article](https://principia-web.se/news/13)** - **[Release](https://github.com/Bithack/principia/releases/tag/2024.02.29)**

- Give the Full health command pad a unique texture
- Revamp networking protocol
- Higher quality sandbox menu icons
- Misc. code cleanups and unused code removal
- **Android:**
  - Now available on F-Droid!
  - Fix x86_64 builds crashing
  - An x86_64 native library is now also provided
- **Linux:**
  - AppImage builds
  - Fix touchscreen input to work like on Windows (hopefully?)
  - Fix Quickadd dialog messing up on some DEs
- **Haiku:**
  - Initial port merged and is available to compile in the source tree

## 2023.12.26 (1.5.2 Beta 2023-12-26)
**[News article](https://principia-web.se/news/12)**

- Sticky note limit has been raised to 32
- Limit of fluid particles has been increased
- Less risk of the game crashing when changing strength of connections
- Switch to CMake for the build system
- **Lua:**
  - `string` and `table` classes are enabled by default, alongside listening on input
  - `bit32` is now available
  - Fix `error(nil)` crashing the game
  - Block unsafe Lua functions
  - Add `entity:is_hidden`
  - Add `world:set_gravity`
  - Add `entity:set_angle`
- **Desktop:**
  - Upgrade to GTK3
- **Windows:**
  - Builds are now linked against UCRT
  - Add portable build (saves user data next to executable, a helper script for running community levels is provided)

## 2023.03.10 (1.5.2 Beta 2023-03-10)
**[News article](https://principia-web.se/news/9)**

- Add ability to toggle GUI with F2
- Use in-game ui::message instead of system toasts on Android (fixes failing game:message)
- Fix various bugs and freezes on Windows (Ball pipeline not working, Level chunk freeze...)
- Add ability to toggle object lock on N
- Removed object and item help texts, it will now open the Wiki instead

## 2022.12.31 (1.5.2 Beta 2022-12-31)
**[News article](https://principia-web.se/news/8)**

- First open source release!
  - Removed DEMO mode, LITE mode and license verification, now completely free and open source.
- New default community site! (principia-web)
  - Communicates with the community site over HTTPS now
  - The game can now play levels from any domain (e.g. the official community site archive)
- Linux support!
- Previously unused objects now available in the sandbox menu ([[Angular Damper]], [[Gear]], [[Magnet]], [[Electromagnet]] and [[Separator]])
  - These objects are partially unfinished and may have bugs or cause crashes. Be careful with them.
- Separator colour can now be configured through config menu
- Items no longer need to be unlocked through the adventure mode
- Object and item help text updates
- 64-bit builds available
- **Desktop:**
  - Window can now be resized
- **Windows:**
  - Installer improvements
- **Android:**
  - Dialog UI update (Holo -> Material)
  - Removed Facebook analytics (yuck)
  - App data now stored in scoped app storage (new API/Google Play requirement)
  - Fixed SFX Emitter dialog
