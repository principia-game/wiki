The Principia protocol `principia://` is used for the game to download and play levels from the community site.

[toc]

## Specification
The Principia protocol contains several arguments separated by slashes.

**`principia://[domain/]action/action_args`**

As of the open source version, if the first argument is not a valid action it is treated as a domain and the game will fetch remote levels from that domain.

There are three actions, `play`, `edit` and `sandbox`.

### Play (`play`)
Play a level or package. It has three arguments: **`play/<type>/<namespace>/<id>`**

- **`type`** can be `lvl` for level, `pkg` for package.
- **`namespace`** is the namespace of the level/package. When playing levels from the community site this is `db`.
- **`id`** is the level/package ID.

### Edit (`edit`)
Open level for editing in sandbox. This is intended for players' own levels, as the community ID is preserved allowing for them to update existing levels on the community site.

### Sandbox (`sandbox`)
Open level for editing in sandbox. This is intended for other players', as it puts the community ID into parent ID, making a level uploaded a derivative of the edited level.

### Comparison: Edit vs. Sandbox
This table shows a comparison of what values get set in the level file by the client, depending on the action.

|                   | Edit   | Sandbox   | Notes                                              |
|-------------------|:------:|:---------:|----------------------------------------------------|
| `community_id`    | `0x1`  | `0x0`     | ID of the level in the community site              |
| `revision`        | `0xB`  | `0x0`     | Internal level revision                            |
| `parent_id`       | `0x0`  | `0x1`     | Community ID of the parent level (for derivatives) |
| `parent_revision` | `0x0`  | `0xB`     | Internal level revision of the parent level        |

## Platform implementation
For desktop platforms, you can always send a Principia protocol link directly to the game executable. This is useful if you are building from source and haven't set up the URL handler but need to quickly play a community level for testing, or are on an in-development platform. Right click on a play button on principia-web and paste it into a command prompt or terminal when calling the game.

```
./principia principia://play/lvl/db/11
```

### Windows
Principia's installer writes an URL handler to the Windows registry. This will use the current location Principia is installed in, but this will break if you for whatever reason were to move the game afterwards without reinstalling. An example of the registry export can be seen here:

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

For portable Windows builds no modifications to the registry are made, and as such the URL handler is not registered. You can use the provided `play_community_level.bat` Batch script which will call the executable for you to play a community level with the inputted ID, or create registry keys manually if you are able to do system modifications. See [Windows Portable#Playing community levels](/wiki/Windows_Portable#playing-community-levels) for more info.

### Linux
The `packaging/` folder contains the [`principia-url-handler.desktop`](https://github.com/Bithack/principia/blob/master/packaging/principia-url-handler.desktop) file which implements the URL handler for a packaged Principia. You should install this file into the `applications` folder when packaging, and package managers such as `pacman` will automatically update the MIME database.

If you do not want to install Principia to your root filesystem, you can copy the URL handler .desktop file to `~/.local/share/applications/` (or the equivalent if `$XDG_DATA_HOME` is defined as something else) and change the `Exec` line to point to where your Principia binary is located, e.g:

```
Exec=/home/rollerozxa/games/principia/principia %u
```

Then to set up the MIME scheme handler association, run the following command in the terminal:

```bash
xdg-mime default principia-url-handler.desktop x-scheme-handler/principia
```

Now when you go into a web browser and press on a level's play button, it should ask you if you want to launch the game.

![](images/principia_protocol.webp)

### Haiku OS
The Principia Haiku port currently does not have any system integration available, so in order to play community levels you will need to call the executable directly. The Haiku port also doesn't have a Principia pipe implemented so it will launch a new game window every time. Contributions by people familiar with Haiku internals are welcome.

### Android
An URL handler is registered by the Android system from the APK's manifest, which should always be available as long as the app is installed.
