This page contains notes for developers who would be interested in porting Principia to a new platform. It is far from comprehensive but should give some information for prospective porters and reduce the amount of trial and error necessary.

## Dependencies
The Principia codebase as a whole is written in a mix of C and C++. The C code requires a compiler that supports C99 and the C++ code requires a compiler that supports C++14. Any relatively recent version of GCC or Clang should be fine.

Principia only supports little endian architecture targets. Big endian is completely untested and it is very likely that some parts of the code will break on a big endian target. Upstream contributions to improve big endian compatibility are appreciated.

Principia uses SDL3 which takes care of most platform-dependent behaviour. If the platform you are porting to already has support in SDL3 then things should go very smoothly. If not then you may consider using or contributing to an SDL port for your platform, if it is not available in mainline SDL it may be unofficially maintained in a fork somewhere.

The current graphics code for Principia needs OpenGL 2.1 or higher, and we use a programmable graphics pipeline with shaders rather than OpenGL's old fixed pipeline. OpenGL ES 2.0 is also available which is used for Android and other things such as the web and mobile Linux. The game can switch between the two at runtime with `use_gles`, but also see `SHOULD_USE_GLES` in the build system which determines which should be the default at compile-time. If your platform does not provide OpenGL you may want to use Zink or ANGLE for translating to other graphics APIs, or Mesa's llvmpipe software renderer in a pinch.

Principia depends on the following libraries for core functionality (in addition to the abovementioned SDL), and needs to be provided but should be portable enough to work on your platform:

- Freetype, for font rendering.
- libpng, for loading PNG textures.
- libjpeg(-turbo), for loading JPEG textures.
- zlib, for various things (satisfying libpng dependency, compressing level files, etc.)

In addition to this Principia has the following technically optional dependencies:

- cURL, for doing communication with a community site over the internet. If you cannot satisfy this dependency you can stub out any reliance on cURL using the dummy network implementation in `network_dummy.cc`.

We also have some vendored libraries in the source tree that may be worth listing:

- Modified version of Box2D+LiquidFun for multithreading and other things specific for Principia. Should not be an issue, but if you get issues with the multithreaded physics simulation you can hardcode the number of logical cores in `settings.cc` to 0 to disable this.
- GLAD for OpenGL (ES) extension wrangling. Should not be an issue, as we load the OpenGL library and functions using SDL.
- Dear Imgui, which is used for various dialogs in the game. Should not be an issue, but if you get issues with Imgui's OpenGL loader you can try using GLAD instead - see the ifdef for Haiku in `imgui_impl_opengl3.cpp`.
- Lua 5.2 for the LuaScript object. Should not be an issue.
- SDL_image, SDL satellite library vendored to reduce dependencies for our official builds. Should not cause any issues.
- SDL_mixer, SDL satellite library vendored to reduce dependencies for our official builds. Should not cause any issues, but you can stub out sounds to remove this dependency if necessary. See `ENABLE_SOUND` in `src/soundmanager.{cc,hh}`

## Building Principia for a new platform
Once you have all the dependencies resolved, you may start to try building Principia. If you are using a cross-compiler toolchain, it will typically provide a CMake toolchain file you can pass when configuring.

When needing to make codepaths specific to your new platform, you should typically use the define that SDL provides. See `SDL_platform_defines.h` in the SDL3 headers.

Some notes that may be useful:

- `src/tms/backend/pipe.cc` contains implementations for IPC between Principia instances, so that when playing levels from the community site it will send a message to the currently running instance of Principia. If this is not relevant for your platform you can just stub this out.
- Debug builds of the game will print to stdout, while release builds will redirect it to a log file (see `redirect_log_output`). See `tms/core/print.h` if you want to entirely customise how the game prints log output to somewhere more accessible for your platform.
- `src/tms/backend/main.cc` is the main entrypoint of the game and contains a lot of platform-specific stuff behind preprocessor gates which may need to be customised for your platform. For example, if your platform does not have the concept of a window but instead just has full control over the screen, you may want to use the Android codepath for determining window size, or hardcode the window size if necessary.

## Contributing
We welcome all patches upstream to improve the portability and platform support of Principia! We would prefer patches for new platforms to be as clean as possible, but some ifdefs to stub out or provide alternate functionality are fine given that they are not too invasive to the primary platforms that we support.
