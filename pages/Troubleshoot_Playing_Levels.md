This page is for troubleshooting playing Principia levels. When pressing the Play button on a level page it should open Principia and download the specified level, but this relies on your system being properly set up to handle `principia://` links. Usually this works without issues, but can have some caveats depending on the platform you are on.

## Try the web version!
If you haven't installed Principia yet, you can try playing levels with the web version of Principia, which should work in any modern web browser with WebGL support. You can find a "Play in browser <span class="beta">(BETA)</span>" link under the level thumbnail on any level page.

## Windows (Installer)
During installation the installer will register the URL handler to where the Principia executable is located. If you have moved the installation files manually without reinstalling then this association will break. Please rerun the installer and install to the new location.

## Windows (Portable)
As the portable Windows version does not make any changes to your system, it won't register the URL handler. You can use the provided `register-protocol-handler.exe` tool to register the URL handler for the current user, which does not require administrator rights.

## Linux
If you have installed a packaged version of the game or use the AppImage version then the URL handler desktop file should be properly installed to your system. Usually your package manager will update the desktop database for you, otherwise you can try running `update-desktop-database` as root to update it manually.

Otherwise if you have built Principia from source and haven't installed or packaged it then you will need to set up the URL handler yourself. See [Principia Protocol#Linux](/wiki/Principia_Protocol#linux) for more details.

## Android
As long as the Principia app for Android is installed, it should be able to handle `principia://` links. [Have you downloaded it yet?](/download)

## macOS/Haiku OS
There is no system integration available for these platforms to automatically handle `principia://` links at the moment, see the below section for playing levels through the terminal.

## If all else fails
You can send `principia://` URLs directly to the Principia executable which it will parse and act upon. So you can copy the link of a level button and paste it into a terminal to pass as an argument to the Principia executable, like such:

```
./principia principia://play/lvl/db/11
```
