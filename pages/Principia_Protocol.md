The Principia protocol `principia://` is used for the game to download and play levels from the community site.

## Specification
TODO

## Platform implementation
For desktop platforms, you can always send a Principia protocol link directly to the game executable. This is useful if you are building from source and haven't installed the game. Right click on a play button on principia-web and paste it into a command prompt or terminal when calling the game.

```
principia.exe principia://play/lvl/db/11
```

### Windows
Principia's installer writes an URL handler to the Windows registry. This will use the current location Principia is installed in, this will break. An example of the registry export can be seen here:

```
[HKEY_CLASSES_ROOT\principia]
@="URL:Principia"
"DefaultIcon"=""
"URL Protocol"=""
[HKEY_CLASSES_ROOT\principia\shell]
[HKEY_CLASSES_ROOT\principia\shell\open]
[HKEY_CLASSES_ROOT\principia\shell\open\command]
@="\"C:\\Program Files\\Principia\\principia.exe\" %1"
```

### Linux
The `build-linux/` folder contains the [`principia-url-handler.desktop`](https://github.com/Bithack/principia/blob/master/build-linux/principia-url-handler.desktop) file which implements the URL handler for a packaged Principia. You should install this file into the `applications` folder when packaging.

If you do not want to install Principia to your root filesystem, you can put the URL handler .desktop file inside of `~/.local/share/applications/` and change the `Exec` line to point to where your Principia is located.

```
Exec=/home/rollerozxa/games/principia/principia %u
```

### Android
An URL handler is registered by the Android system from the APK's manifest.