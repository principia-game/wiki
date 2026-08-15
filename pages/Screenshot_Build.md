The Principia screenshot build is a special build of the game that can take screenshots of levels at designated [[Cam Marker]]s, alternatively at the last saved position if no Cam Markers exist.

The screenshot build is only supported on Linux, and can be enabled by passing `-DSCREENSHOT_BUILD=ON` to CMake.

## Dependencies
The screenshot build is more minimal than a regular build, due to not requiring the full game to be playable and it usually runs in an embedded environment. The following dependencies required for a regular build of the game is not required for the screenshot build:

- cURL (No network communication is necessary, levels need to be provided locally)

## Usage
To run the screenshot build, you need some way of rendering graphics. This may sound obvious, but the screenshot build is generally meant to be run on a headless server.

When deploying the screenshotter onto a headless server, you may want to use Mesa's llvmpipe software renderer to render the game without a GPU. You may also use SDL's offscreen video driver (set the `SDL_VIDEO_DRIVER=offscreen` environment variable) to not require a virtual X server or similar to contain the game window.

Once you have an environment simply run the `principia` executable. The data directories need to be next to the executable, and various files will be written in the same folder. For the structure and information of what files and folders gets written and read see the following:

```
- /principia/         (this folder can be anywhere and called anything)
  - data/             Data folder
  - storage/          User data directory
  - principia         Screenshot build executable
  - principia.state   The state the screenshotter is in (e.g. in progress or resting)
- /tmp/
  - principia_cache/  Cache folder used for the screenshot build
  - principia.run     Unix pipe, used for IPC and connecting to an existing Principia instance
```

When the screenshot build is launched with no arguments and it finishes loading, it will enter an idle state with the text "Screenshotter is ready and listening on pipe...". In this idle state, it is waiting for a message to be sent over the Unix pipe.

To take a screenshot of a level, simply send a Principia prototol URL over the pipe by running the Principia executable again. For example, if we have placed a level file `2.plvl` into `/tmp/principia_cache/lvl/db/`, we can then run the following

```
./principia principia://play/lvl/db/2
```

The screenshotter will receive this and open the level, starting to take screenshots. They will be saved as PNG files next to the executable with incrementing filenames (ss-0.png, ss-1.png, etc.). When the screenshotter is done, it will return to the idle state and be ready for the next level.

## Uses
For production use with principia-web, the screenshotter is run in a headless Docker container using Alpine and Mesa llvmpipe for software rendering. The files to build the container image can be found [here](https://github.com/principia-game/screenshotter-container).

In the principia-web repository there is a script [`take_screenshot.sh`](https://github.com/principia-game/principia-web/blob/master/tools/take_screenshot.sh) which is used to take screenshots using the container, pushing in level files and pulling out the resulting screenshot.
