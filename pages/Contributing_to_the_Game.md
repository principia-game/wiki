This page contains information for developers who would want to contribute to the development of Principia.

Principia is a physics-based sandbox game originally developed as a commercial game by Bithack between 2012-2014 before being abandoned due to financial issues. In 2022 the source code was released as open source and maintenance of the game has been picked up to be maintained by the Principia community.

Due to this legacy the codebase is in a rather rough shape and there are a lot of bugs and other issues with the game that never got fixed. As with any other small open source project, we always lack time and would appreciate any contributions we can get by people who are interested in the game and would like to use their programming knowledge to see it become even better.

This page is far from exhaustive but hopes to give a brief overview of what you might want to know as a prospective contributor.

[toc]

## Communication
The canonical source repository for the game is on [Github](https://github.com/Bithack/principia/), where the issue tracker is and where you can submit pull requests. Not all issues are properly labelled but there are always a lot of bug reports to sift through.

When it comes to more real-time communication for the game's development we have the `#development` channel in the [Principia Discord server](https://principia-web.se/discord). Please stop by if you want to discuss any things related to development or have other questions relating to development. Most of the active community members reside in Europe so if you write something when it is past midnight there please be patient for a response.

We are aware both of these platforms are operated by corporations that act in the opposite interest of Free software, and you do not need to remind us. We would like to bridge our chat to Matrix, we used to have a Matrix space but was shut down due to the Matrix bridge service we used being broken most of the time leaving it in an unusable state, and we do not have the resources to host our own. If you would be willing to host a bridge for Principia then this would be very appreciated.

## Compiling and developing
Compiling the game should be simple on Linux, and shouldn't be very difficult on Windows either. See [[Compiling Principia]] for instructions for the particular platform.

For inspiration on setting up a development environment, ROllerozxa uses [VSCodium](https://vscodium.com/) (actually Code - OSS) along with the [clangd](https://open-vsx.org/extension/llvm-vs-code-extensions/vscode-clangd) extension for general C/C++ language features and [CodeLLDB](https://open-vsx.org/extension/vadimcn/vscode-lldb) for running the game in a debugger. This should be possible to set up both on Linux as well as on Windows, but if you have any other setup for C/C++ development that does not use MSVC it should work well for Principia.

As we also support Android, it would be nice to also test that things work on Android too. The compilation guide shows a way to build Principia for Android using just the command-line tools without using Android Studio and install it onto an Android device you hopefully may have.

## Technologies
The Principia game codebase is written in C++ while the backing (in-house) game engine TMS is written in C. But even then, if you look into the C++ Principia codebase you may see that it is at times written in a very "C-y" way, so to speak.

For graphics rendering we use OpenGL (2.1) as well as being able to use OpenGL ES 2.0 for platforms where OpenGL is not available.

We use SDL2 to abstract away most platform-specific aspects of the game, but we have some platform-specific codepaths where SDL2 falls short. Other than that the core of Principia is very portable, see [[Porting Principia]] for more information.

## Documentation
There is not a lot of written down documentation, the code is mostly the documentation. Some parts of the codebase are better commented than other, but you will likely have to do a lot of exploration on your own.

We have automatically generated Doxygen documentation for the codebase available at https://doxy.principia-web.se/. It gets automatically updated on new commits to the Principia repository. If you would want to begin documenting the codebase then you'd want to do so in a way that Doxygen can use it to improve the generated output.

You may get some more information by word-of-mouth asking about things in the development channel, but keep in mind that the original developers of the game that would know about the juiciest details are not around anymore. In most cases we are likely just as confused about various things in the code as you are.

## Compatibility
Generally we would like to keep full compatibility with levels as much as we can. There is a version value inside of each level file which can be used to make breaking changes while keeping old levels working the same. Undocumented behaviour (e.g. [[Hacked Signals]]) can be changed if there is a good reason to do so but generally the playback of existing levels should stay the same.

Anything else of the game (e.g. the UI and rendering engine) is more flexible to change, but keep in mind players' [existing workflow](https://xkcd.com/1172/) in the sandbox - the game has been around for over a decade and muscle memory is very strong.
