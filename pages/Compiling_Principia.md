Below are instructions to build Principia from source on all supported platforms, as well as notes for getting Principia to run on certain hardware.

If you have issues building Principia, then please ask in the `#development` channel on Discord.

[toc]


## Linux
If you just want to play Principia on Linux, there is an AppImage build available as well as packages for various Linux distributions. If these don't work or you want to build from source for emotional reasons then follow along.

First of all install the dependency packages for your respective distro branch.

**Debian-based distros:**

```bash
sudo apt install --no-install-recommends cmake ninja-build libgtk-3-dev libgl-dev libglew-dev libcurl4-openssl-dev libpng-dev libjpeg-dev libfreetype6-dev libsdl2-dev
```

**For Arch-based distros:**

```bash
sudo pacman -S --needed cmake ninja glew gtk3 curl freetype2 libpng libjpeg sdl2
```

**For Fedora:**

```bash
sudo dnf install @development-tools cmake ninja gcc-c++ freetype-devel libcurl-devel libpng-devel libjpeg-turbo-devel gtk3-devel SDL2-devel libXxf86vm-devel glew-devel mesa-libGLU-devel alsa-lib-devel systemd-devel
```

**For Alpine:**

```bash
doas apk add build-base cmake ninja mesa-dev glew-dev gtk+3.0-dev libpng-dev jpeg-dev curl-dev freetype-dev zlib-dev sdl2-dev
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
On Linux Principia will attempt to load data from the following directories:

1. `./` (data directories are next to the executable)
2. `../` (data directories are one directory up relative to the executable)
3. `./share/principia/` (for an installed build)

When doing `ninja install`, the data folders will be installed to `share/principia`. For packaging, you would want to pass `-DCMAKE_INSTALL_PREFIX=/usr` to CMake which when installed will put data where it can get loaded from.


## Windows
The game engine behind Principia (TMS) is written in the C99 standard of C. Unfortunately, the Visual Studio C compiler does not support the C99 standard. Principia must therefore be compiled using MinGW-w64 toolchain.

The following Windows build instructions use MSYS2 which is a development environment for Windows including MinGW and other tools. Please [download the latest version of the MSYS2 installer here](https://www.msys2.org) and install it.

After installation, a terminal opens. Run the following command to update the environment:

```bash
pacman -Syu
```

The terminal will then ask you to shut down the MSYS2 runtime to the finish the update. Proceed with doing so, and then go to the start menu and start the "MSYS2 UCRT64" environment (icon with gold background) again. Run the following command to install the necessary dependencies:

```bash
pacman -S git mingw-w64-ucrt-x86_64-{gcc,cmake,ninja,curl-winssl,gtk3,glew,libpng,libjpeg-turbo,freetype,SDL2}
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

When finished there will be a `principia.exe` file in the build folder. Keep in mind that the built executable can only be run inside of the MSYS2 terminal, to package up the game and make it runnable outside see the below section.

### Packaging for Windows
The Windows installer uses NSIS, which must be installed first before building:

```bash
pacman -S mingw-w64-ucrt-x86_64-nsis
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


## Haiku OS
An initial port to Haiku OS is available and has now been merged into master. To build Principia on Haiku simply clone the repository and proceed with the build instructions.

Install dependencies:

```bash
pkgman install cmake ninja curl_devel freetype_devel glew_devel gtk3_devel libjpeg_turbo_devel libpng16_devel libsdl2_devel
```

Then build using CMake like usual:

```bash
mkdir build; cd build
cmake .. -G Ninja
ninja
```

An executable `principia` should be produced once finished which you use to run the game.

While most of the game should work fine as it uses SDL2 and other cross-platform libraries, some platform-specific plumbing such as the URL protocol handler and piping is not implemented on Haiku yet (see [#146](https://github.com/Bithack/principia/issues/146) for a TODO). As a workaround, you can play community levels on Haiku by launching Principia with the URL used by the level's "Play" button link as the first argument (see [[Principia Protocol]]).


## Notes

### Raspberry Pi
Principia works fine on a Raspberry Pi, just follow the regular compilation steps for the Linux distro branch of your choosing.

### Chrome OS
If your Chromebook is relatively recent, it supports running Linux inside of a container in Chrome OS with [Crostini](https://chromeos.dev/en/linux). Principia should run fine inside of this container, obtain it like you would with any other Linux system. If your Chromebook is x86_64 based then the AppImage should work, otherwise then follow the build steps for the distribution you're using in the container.

### Cross-compile for Windows on Linux
You can compile Principia for Windows on a Linux distro that uses pacman by adding MSYS2's UCRT64 repository which provides all the dependencies Principia needs, and then running their GCC compiler build under Wine. While the packages are all mostly self-contained to `/ucrt64/` and ROllerozxa has had success building Principia like this without destroying his system in the process, this is almost definitively not supported by either MSYS2 or your Linux distro and caution is advised when doing this.

Install the latest `msys2-keyring` package from [the MSYS2 mirror repo](https://repo.msys2.org/msys/x86_64/) and install it. Then go into your `/etc/pacman.conf` and add the following lines to add the `ucrt64` repository:

```conf
[ucrt64]
Server = https://mirror.msys2.org/mingw/$repo/
```

Run `sudo pacman -Syu` to update the database and then proceed to install all dependencies like seen in the Windows instructions.

Clone the repository and create a build folder. Then navigate into the build folder with a terminal and run `wine cmd` to start a Wine command prompt. Add the binaries provided by MSYS2 to the path:

```batch
set PATH=Z:\ucrt64\bin\;%PATH%
```

Then within this command prompt, run `cmake` to generate build files and then run `ninja` to begin the build.
