For information on compiling Principia from source, [see the "Building and running" section in the README](https://github.com/Bithack/principia#building-and-running).

Below are also some miscellaneous notes for running Principia on particular platforms.

## Notes

### Raspberry Pi
Principia works fine on a Raspberry Pi (tested by ROllerozxa on a Pi 4B running Arch Linux ARM), just follow the regular compilation steps for the Linux distro branch of your choosing.

### Chrome OS
If your Chromebook is relatively recent, it supports running Linux inside of a container. Principia should run fine inside of this container, obtain it like you would with any other Linux system. (tested by ROllerozxa on an ASUS C213N Chromebook with an Arch Linux container)

### Haiku OS
An initial port to Haiku OS is available and has now been merged into master. To build Principia on Haiku simply clone the repository and proceed with the build instructions.

Install dependencies:

```bash
pkgman install cmake ninja curl_devel freetype_devel glew_devel gtk3_devel libjpeg_turbo_devel libpng16_devel libsdl2_devel
```

Then build using CMake like usual:

```
mkdir build; cd build
cmake .. -G Ninja
ninja
```

An executable `principia` should be produced once finished which you use to run the game.

While most of the game should work fine as it uses SDL2 and other cross-platform libraries, some platform-specific plumbing such as the URL protocol handler and piping is not implemented on Haiku yet (see [#146](https://github.com/Bithack/principia/issues/146) for a TODO). As a workaround, you can play community levels on Haiku by launching Principia with the URL used by the level's "Play" button link as the first argument (see [[Principia Protocol]]).
