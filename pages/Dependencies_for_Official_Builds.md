This page contains an overview of where the dependency libraries for official builds (produced by CI) come from.

## Windows
We use [MSYS2](https://www.msys2.org/) to obtain our compiler toolchain as well as most library dependencies.

We have custom builds for the following dependencies:

- cURL: Unnecessary components disabled to reduce final package size
- Freetype: Unnecessary components disabled to reduce final package size

The buildscripts are available in [principia-game/windows-deps](https://github.com/principia-game/windows-deps). These are built by CI on each commit to the dependency repository and uploaded to a Github release that the Principia CI then downloads.

## Linux
The official AppImage builds are built in a Debian container in the CI, so libraries from Debian's repositories end up bundled in the AppImage where it is not assumed that they exist on the target system (e.g. Freetype and cURL are stable enough and should exist on the target system).

We build our own version of SDL3 as part of the build process (`-DUSE_VENDORED_SDL3=ON`) to ensure that we get the latest version of SDL3 with the game, as the version of Debian we build on does not even include SDL3 in its repositories.

## Android
For Android we manage all our dependencies, and buildscripts are available in [principia-game/android-deps](https://github.com/principia-game/android-deps). These are built by CI on each commit to the dependency repository and uploaded to a Github release that the Principia CI then downloads.

Specifically for SDL, the Principia repository contains Java glue code for SDL at `build-android/principia/src/main/java/org/libsdl/app/`. Currently this has been modified by Principia, but should be more cleanly separated sometime in the future. To update SDL on Android you will need to apply any changes that were made in SDL upstream's glue code while keeping Principia-related changes intact.

## macOS
We obtain all dependencies from [Homebrew](https://brew.sh).
