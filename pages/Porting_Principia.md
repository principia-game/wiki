This page contains notes for developers who would be interested in porting Principia to a new platform. It is far from comprehensive but should give some information for prospective porters and reduce the amount of trial and error necessary.

## Dependencies
The Principia codebase as a whole is written in a mix of C and C++. The C code requires a compiler that supports C99 and the C++ code requires a compiler that supports C++14. Any relatively recent version of GCC or Clang should be fine.

Principia only supports little endian architecture targets. Big endian is completely untested and it is very likely that some parts of the code will break on a big endian target. Upstream contributions to improve big endian compatibility are appreciated.

Principia uses SDL2 which takes care of most platform-dependent behaviour. If the platform you are porting to already has support in SDL2 then things should go very smoothly. If not then you may consider using or contributing to an SDL port for your platform, if it is not available in mainline SDL it may be unofficially maintained in a fork somewhere.

The current graphics code for Principia needs OpenGL 2.1 or higher. OpenGL ES 2.0 is also available which is used on Android as well as on niche Linux builds, see `TMS_USE_GLES`. In a pinch, software rendering using Mesa's software renderer may be acceptable for porting if it exists on your platform.

Principia depends on the following libraries for core functionality (in addition to the abovementioned SDL), and needs to be provided but should be portable enough to exist on your platform:

- Freetype, for font rendering.
- libpng, for loading PNG textures.
- libjpeg(-turbo), for loading JPEG textures.
- zlib, for various things (satisfying libpng dependency, compressing level files, etc.)

In addition to this Principia has the following dependencies that may be provided:

- cURL, for doing communication with a community site over the internet. If you cannot satisfy this dependency you can stub out any reliance on cURL by undefining `BUILD_CURL` in `src/src/main.cc`.
- GTK3 for some dialogs. This is a **very big** one, and can likely not be satisfied unless your platform is very desktop-like. We are working on removing this dependency by switching dialogs to using Dear Imgui which is much more portable and will work on anywhere with OpenGL(ES) that Principia uses. As a stop-gap measure, you can make use of the dummy dialog implementation found in `src/src/ui.cc`.

We also have some vendored libraries in the source tree that may be worth listing:

- Lua 5.2 for the LuaScript object. Should not be an issue.
- Luasocket for providing networking functionality to LuaScript. Not used a lot by levels and may cause portability issues, `BUILD_LUASOCKET` (`USE_LUASOCKET` in CMake) controls building it if you need to disable it.
- SDL_image, SDL satellite library vendored to reduce dependencies for our official builds. Should not cause any issues.
- SDL_mixer, SDL satellite library vendored to reduce dependencies for our official builds. Should not cause any issues, but you can stub out sounds to remove this dependency if necessary. See `ENABLE_SOUND` in `src/src/soundmanager.{cc,hh}`

## Adding a new platform
In `CMakeLists.txt` add detection for the new platform to set an appropriate `TMS_BACKEND` preprocessor define in the "Determine platform and backend" section.

In `src/tms/core/backend.h`, add a line for defining `OS_STRING` using the preprocessor define you just added in the CMake code. If you manage to get far enough with the port then this will used for levels uploaded from this platform, so it should be a human readable name for your platform.

After that you are mostly on your own and will need to do your judgement based on the platform you are porting to.
