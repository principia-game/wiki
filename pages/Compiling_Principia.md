Below are instructions to build Principia from source on all supported platforms, as well as notes for getting Principia to run on certain hardware.

If you have issues building Principia, then please ask in the `#development` channel on [Discord](/discord) (also available on [Fluxer](/fluxer)).

[toc]

## Linux
If you just want to play Principia on Linux, there is an AppImage build available as well as packages for various Linux distributions available [on the download page](/download). If these don't work or you want to build from source for emotional reasons then follow along.

First of all install the dependency packages for your respective distro branch.

> **Note:**
>
> Principia has upgraded from SDL2 to SDL3. If you are e.g. on a distribution that does not have SDL3 available in your package repositories yet, you can use `-DUSE_VENDORED_SDL3=ON` when running CMake to download and build a copy of SDL3 from source as part of the build process. See [the SDL wiki](https://wiki.libsdl.org/SDL3/README-linux) for dependencies that SDL3 needs on Linux.

**Debian-based distros:**

```bash
apt install --no-install-recommends g++ cmake ninja-build libcurl4-openssl-dev libfreetype6-dev libgl-dev libgtk-3-dev libjpeg-dev libpng-dev libsdl3-dev
```

**For Arch-based distros:**

```bash
pacman -S --needed gcc cmake ninja curl freetype2 gtk3 libjpeg libpng sdl3
```

**For Fedora:**

```bash
dnf install gcc-c++ cmake ninja-build libcurl-devel freetype-devel gtk3-devel libjpeg-turbo-devel libpng-devel SDL3-devel
```

**For Alpine:**

```bash
apk add g++ cmake ninja curl-dev freetype-dev gtk+3.0-dev jpeg-dev libpng-dev sdl3-dev
```

Navigate somewhere you want to clone the Principia source code to and clone the source repository using Git (install the `git` package for your distro if you somehow haven't already):

```bash
git clone https://github.com/Bithack/principia
cd principia
```

Generate the build files using CMake and start compilation:

```bash
mkdir build; cd build
cmake .. -G Ninja
ninja
```

When finished a `principia` executable will be produced, which can then be run.

While the game works fine when being run from out of the source tree, additional setup is required for the URL handler to work in order to play community levels. See [this page on the Wiki](https://principia-web.se/wiki/Principia_Protocol#linux) for more details.

### Packaging for Linux
See [[Information for Downstream Packagers]].


## Windows
Principia can only be built for Windows with a mingw-w64 toolchain, whether it be using GCC or LLVM. MSVC is not supported at the moment and it is unknown if Principia can be compiled with it as MSVC has historically lacked support for C99 which Principia's engine TMS is written in.

The following Windows build instructions use [MSYS2](https://www.msys2.org) which is a development environment for Windows that includes mingw-w64, libraries and other tools. Please [download the latest version of the MSYS2 installer here](https://www.msys2.org) and install it.

After installation, a terminal opens. Run the following command to update the environment:

```bash
pacman -Syu
```

The terminal will then ask you to shut down the MSYS2 runtime to the finish the update. Proceed with doing so, and then go to the start menu and start the "MSYS2 CLANG64" environment (icon with orange background). Run the following command to install the necessary dependencies:

```bash
pacman -S mingw-w64-clang-x86_64-{clang,cmake,ninja,curl-winssl,git,gtk3,libpng,libjpeg-turbo,freetype,sdl3}
```

Navigate somewhere you want to clone the Principia source code to, such as on your desktop:

```bash
cd /c/Users/$USER/Desktop/
git clone https://github.com/Bithack/principia
cd principia
```

Then generate the build files using CMake and start the compilation:

```bash
mkdir build; cd build
cmake .. -G Ninja
ninja
```

When finished there will be a `principia.exe` file in the build folder. Keep in mind that the built executable can only be run inside of the MSYS2 terminal, unless you package it up.

While the game works fine when being run from out of the source tree, additional setup is required for the URL handler to work in order to play community levels. See [this page on the Wiki](https://principia-web.se/wiki/Principia_Protocol#windows) for more details.

### Packaging for Windows
The Windows installer uses NSIS, which must be installed first before building:

```bash
pacman -S mingw-w64-clang-x86_64-nsis
```

For making Windows release builds you would run the `packaging/windows_release.sh` script, which will bundle necessary DLLs and other files to make the game run, and builds the installer. The `packaging/windows_portable.sh` script can be used to generate a portable release, which depends on the installer script being run first to work.


## Android
These instructions will use the command-line tools. They are more lightweight than the big and heavy Android Studio and should work fine if you just want to build from source on Android or do some light work on it.

The instructions assume you are on some kind of Linux system. You should also have a recent version of OpenJDK installed (17 should be enough).

Download the command line tools from the bottom of [the Android Studio downloads page](https://developer.android.com/studio). Then extract it into an empty folder with the structure being as seen below. the `android-sdk` folder will then become your SDK folder.

```
- android-sdk/
	- cmdline-tools/
```

Then open a terminal in `android-sdk/` and run the following command to accept the licenses for the SDK. Accept the licenses that you definitively should read carefully.

```bash
./cmdline-tools/bin/sdkmanager --licenses --sdk_root=.
```

Clone the Principia repository if you haven't already and go into `build-android`. Create a file called `local.properties` and put the following line that should point to where you put the Android SDK:

```conf
sdk.dir=/home/<YOUR USER>/android-sdk
```

With a terminal in the `build-android` directory, run the following command:

```bash
./gradlew assembledebug
```

It should begin downloading the NDK and other additional components on its own before building Principia. A debug build will be produced which will be automatically signed with a debug key. You can then install this onto a connected phone or emulator using `./gradlew installdebug`.

To make a release build run `./gradlew assemblerelease`. The release build will not be signed by default so you will need to bring your own signing key to sign with `apksigner` yourself.


## macOS
**Note**: macOS support is very experimental and will likely have issues or not work at all. Contributions are welcome, and let us know how well it works.

First of all install [Homebrew](https://brew.sh). Then in the terminal install dependencies:

```sh
brew install cmake ninja libpng libjpeg-turbo freetype sdl3 gtk+3
```

Then go into the cloned Principia source directory and generate build files:

```bash
mkdir build; cd build
cmake .. -G Ninja
cmake .. -DCMAKE_EXE_LINKER_FLAGS="-L/usr/local/lib/"
```

If you have Homebrew installed anywhere else than `/usr/local/` (see [Homebrew's docs](https://docs.brew.sh/FAQ#why-should-i-install-homebrew-in-the-default-location)) then change the above commands to point to where it is.

Build:

```bash
ninja
```

When compilation finishes an executable `principia` should be produced once finished which you can run from the terminal.

### Packaging for macOS
The build system can create a macOS app bundle. Simply run `ninja package` in the build directory and a .zip file should be produced with an app bundle inside.


## Haiku OS
An initial port to Haiku OS is available and has now been merged into master. To build Principia on Haiku simply clone the repository and proceed with the build instructions.

Install dependencies:

```bash
pkgman install cmake ninja curl_devel freetype_devel gtk3_devel libjpeg_turbo_devel libpng16_devel libsdl3_devel
```

Then build using CMake like usual:

```bash
mkdir build; cd build
cmake .. -G Ninja
ninja
```

An executable `principia` should be produced once finished which you use to run the game.

While most of the game should work fine as it uses SDL3 and other cross-platform libraries, some platform-specific plumbing such as the URL protocol handler and piping is not implemented on Haiku yet (see [#146](https://github.com/Bithack/principia/issues/146) for a TODO). As a workaround, you can play community levels on Haiku by launching Principia with the URL used by the level's "Play" button link as the first argument (see [[Principia Protocol]]).

## Web
**Note**: Web support is very experimental and has a lot of issues that still haven't been resolved. Contributions are welcome, and let us know how well it works.

You will need to install [Emscripten](https://emscripten.org/) to compile Principia for the web.

Then invoke CMake through Emscripten's `emcmake` wrapper and compile the game:

```bash
mkdir build; cd build
emcmake .. -G Ninja
ninja
```

The resulting output can be quickly tested in your browser with Emscripten's built-in web server using `emrun`:

```bash
emrun principia.html
```
