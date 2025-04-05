This page contains information for packagers looking to package Principia for their Linux distro.

## Metadata
- **License**: Principia is licensed under the BSD 3-Clause license applying both to code and media. However there are vendored libraries licensed under MIT and zlib that may need to be mentioned depending on packaging guidelines.
- **Short description**: "Physics-based sandbox building game"
- **Website**: https://principia-web.se
- **Repository**: https://github.com/Bithack/principia

Some other metadata information can be found in the Principia metainfo file at `packaging/se.principia_web.principia.metainfo.xml`.

## Dependencies
We use CMake for our build system which you would want to add as a buildtime dependency. Our documentation uses Ninja but using the regular CMake Makefile generator is fine too.

GCC's optimisations are prone to causing various bugs with the game, and while we have managed to resolve some of them, building with Clang is highly recommended for stability. However GCC is still supported if necessary and we are welcome to fixes that improve the situation when building with GCC.

Principia relies on the following runtime dependencies:

- cURL
- Freetype
- GTK3
- libpng
- libjpeg(-turbo)
- SDL2
- zlib

None of these libraries are vendored, and the build system uses the versions provided by the system when building. You are welcome! :)

In addition to this Principia uses `xdg-open` for opening webpages from the game. Whether it can be assumed to exist on the base system or a dependency on `xdg-utils` should be added is up to you.

### Vendored libraries
If you peek in `src/` you may see that there are some more libraries we use that are vendored.

SDL_image and SDL_mixer are vendored to reduce the amount of libraries that are pulled in for our official Windows and Linux builds, as well as being used for the Android version. Devendoring these libraries should not cause any adverse effects and you are free to do so.

Principia has vendored versions of Lua 5.2, Luasocket and Box2D. Do **not** under **any circumstances** devendor these libraries, as they have modifications done to them for use with the game. Even if you manage to replace it with system libraries, the physics simulation will be significantly altered breaking existing levels and you will likely expose dangerous functions in the Lua scripting.

We understand the security concerns with vendoring libraries, and we proactively look out for potential vulnerabilities or other bugs that have been patched in upstream. If you are aware of any issues in the vendored libraries then please let us know.

## Files
Principia provides the usual metadata files for packaging such as an icon and desktop file, and it should be as easy as doing `ninja install` with `DESTDIR` pointed to your packaging system's package directory. It will install everything including the binary and game data in a way that the game can read data as long as the directory structure is kept, and as long as your distro follows the traditional Linux directory structure that should be all you need.

To be more detailed, Principia attempts to load the data folders `data-pc` and `data-shared` from the following locations:

1. `./` (data directories are next to the executable)
2. `../` (data directories are one directory up relative to the executable)
3. `../share/principia/` (for an installed build)

So while Principia would usually be installed at `/usr/bin/principia` and its data in `/usr/share/principia/`, the binary is relocatable and the prefix could be something completely else than `/usr` such as e.g. `/usr/local` or `/packagesilo/principia`. If your distro doesn't use `/usr` you probably are already aware of this.

## Network connections
Principia makes connections to principia-web by default. Inform the user of this network connectivity in the metadata of the package, if necessary. The source code for the website is available [here](https://github.com/principia-game/principia-web) licensed under the AGPLv3 license, and also see the [Privacy Policy](/privacy).

Do **not** patch out any of the game's network connectivity, a large part of the game is the community site where you can play and upload levels.

If you are still required to disable the network connectivity that happens by default, then please only replace the default community domain located in the top of `populate_community_host()` in `src/src/main.cc` with `localhost` or something else. This makes the player still able to play levels from level servers in their web browser and reactivate full network connectivity by putting a domain (e.g. `principia-web.se`) in `community_host.txt` in their Principia user folder.

Do **not** remove the update check. Principia does not automatically update, it simply shows a toast message on the main menu that a new version is available. The player deserves to be able to know if the packaged Principia they have installed is outdated, as it may make it impossible to play new levels made with newer versions when new features are added and the level version is increased.

## Upstream communication
When you've gotten Principia packaged for your distribution it would be great to hear from you, so the package can be added in a section on the download page.

Any kind of patches to the game that are general enough to be upstreamed to us are very welcome. Either open a pull request on Github or send an email to ROllerozxa linking to the patches and he can take a look at them.
