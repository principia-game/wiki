This page contains the changelog for Principia.

For versions prior to the source code release, please see [[Old Changelog]].

[toc]

## 2024.XX.XX (future release)
- Merge sound data directories across platforms (makes sounds stereo on Android and fixes some missing sound files)
- Fix crash when attempting to save the state of a level with a LuaScript in it
- Revert to old colour picker on desktop (makes it easier to select Pixel alpha)
- Allow changing the community site domain at runtime
- Fix building with GCC 14
- Various code cleanups
- **Lua:**
  - Add `entity:set_fixed_rotation`
  - Add `entity:is_fixed_rotation`
  - Add `entity:apply_force`
- **Desktop:**
  - Allow storing user data portably on all desktop platforms (not just Windows)
  - Show an error message when a segfault crash happens
- **Windows:**
  - Fix installer installing duplicate data-shared folder
  - Fix segfault on very old unsupported OpenGL versions (it gives a more friendly error instead)
- **Linux:**
  - Don't use Debian's broken SDL2 library for AppImage
- **Android:**
  - Switch to CMake
  - Drop support for Android KitKat (5.0 Lollipop is now minimum)
- **macOS:**
  - Experimental port to macOS now available!

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
