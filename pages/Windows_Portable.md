The portable Windows release is distributed in a .7z archive as an alternative to the installer and can be extracted to be played anywhere and everywhere, without requiring the game to be installed.

In Windows 11 Explorer has built-in support for opening .7z archives. Otherwise you should install [7-zip](https://7-zip.org/) in order to open the archive (other archiving programs should also be able to open .7z archives).

While the installer is to be preferred, the portable version is useful if you want to play Principia on a computer where you lack administrator rights, or to put Principia on a thumbdrive and be stored self-contained within a folder.

## Playing community levels
As the portable version doesn't make any changes to the system, attempting to play community levels by simply pressing a button on the community site will not work out of the box. You can use the bundled `register-protocol-handler.exe` tool to register the protocol handler for the current user, which does not require administrator rights.

## User data
User data is stored in a `./userdata/` folder next to the executable, as compared to in `C:\Users\<username>\Principia\` with installer builds. This is controlled by the `portable.txt` file next to the executable. If you want data to be stored in the regular location then delete this file, and Principia will store user data like an installer build.

## Updating
To update a portable build of Principia, simply extract the new version somewhere and move over your `userdata` folder from the old version's folder. You may now delete the old version's folder and replace it with the new one.
