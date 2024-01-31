The portable Windows release is distributed in a .7z archive as an alternative to the installer and can be extracted to be played anywhere and everywhere, without requiring the game to be installed.

In Windows 11 Explorer has built-in support for opening .7z archives. Otherwise you should install [7-zip](https://7-zip.org/) in order to open the archive (other archiving programs should also be able to open .7z archives).

While the installer is to be preferred, the portable version is useful if you want to play Principia on a computer where you lack administrator rights, or to put Principia on a thumbdrive and be stored self-contained within a folder.

[toc]

## Playing community levels
As the portable version cannot register the necessary registry keys for the URL protocol, attempting to play community levels by simply pressing a button on a community site will not work like it does in the installer version.

### Helper program
If you do not want to make any changes to the system (i.e. no administrator rights or Principia is stored on a thumbdrive) there is a Batch script included in the portable archive called `play_community_level.bat`. It is an interactive command-line program that can help you play community levels by passing a level ID onto the game to download and play from the community site of your choosing. After you have chosen a community site, the window will stay up allowing you to input another level ID, until you choose to close it.

### Registry
If you are willing to modify the system in order to register the URL protocol handler for the portable build, you can manually register a registry key pointing to the executable. For example:

```reg
[HKEY_CLASSES_ROOT\principia]
@="URL:Principia"
"DefaultIcon"=""
"URL Protocol"=""
[HKEY_CLASSES_ROOT\principia\shell]
[HKEY_CLASSES_ROOT\principia\shell\open]
[HKEY_CLASSES_ROOT\principia\shell\open\command]
@="\"C:\\Users\\ROllerozxa\\Desktop\\Principia\\principia.exe\" %1"
```

Note that for path delimiters, you need to use double backslashes (`\\`) to escape them. Save the above code with the correct path to the `principia.exe` executable to a file with a `.reg` file extension, and double click it. Windows will ask if you want to apply the registry changes, say yes.

If you go onto a level and press the play button, your browser should recognise the protocol handler and call Principia accordingly to play the selected community level.

## User data
User data is stored in a `./userdata/` folder next to the executable, as compared to in `C:\Users\<username>\Principia\` with installer builds. This is controlled by the `portable.txt` file next to the executable. If you want data to be stored in the regular location then delete this file, and Principia will store user data like an installer build.

## Updating
To update a portable build of Principia, simply extract the new version somewhere and move over your `userdata` folder from the old version's folder. You may now delete the old version's folder and replace it with the new one.
