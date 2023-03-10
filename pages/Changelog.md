This page contains the changelog for Principia. For versions prior to the open sourcing, please see [the source tree](https://github.com/Bithack/principia/tree/master/doc/changes).

## 1.5.2 (unreleased)
*This is the changelog for an upcoming version. The list of changes is subject to change during development. See the [1.5.2 roadmap](https://github.com/Bithack/principia/issues/64) for more information.*

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
- Opening the object or item help takes you to the Wiki now
- 64-bit builds available
- **Desktop:**
  - Window can now be resized
  - Add ability to toggle GUI with F2
  - Add ability to toggle object lock with N
- **Windows:**
  - Installer improvements
- **Android:**
  - Dialog UI update (Holo -> Material)
  - Removed Facebook analytics (yuck)
  - Use in-game ui::message instead of native toasts (fixes toasts that don't show up)
  - App data now stored in scoped app storage (new API/Google Play requirement)
  - Fixed SFX Emitter dialog