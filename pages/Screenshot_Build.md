The Principia screenshot build is a special build of the game that can take screenshots of levels at designated [[Cam Marker]]s, alternatively at the last saved position if no Cam Markers exist.

The screenshot build only supports Linux, and can be enabled by passing `-DSCREENSHOT_BUILD=ON` to CMake. When enabled, the `screenshot-linux` TMS backend is used as compared to the `linux` backend, and reports its platform as `Linux_SS` (`TMS_BACKEND_LINUX_SS`).

## Dependencies
The screenshot build is more minimal than a regular build, due to not requiring the full game to be playable and it usually runs in an embedded environment. The following dependencies required for a regular build of the game is not required for the screenshot build:

- cURL (No network communication is necessary, levels need to be provided locally)
- GTK3 (No dialogs are shown)
- SDL2_mixer (No sound)

## Usage
To run the screenshot build, you need some way of rendering graphics. This may sound obvious, but the screenshot build is generally meant to be run on a headless server. For this, you will need to install Xvfb which allows you to start an X server running in a virtual framebuffer without needing a monitor, as well as the Mesa3D software driver for rendering OpenGL.

Once you have an environment simply run the `principia` executable. The data directories need to be next to the executable, and various files will be written in the same folder. For the structure and information of what files and folders gets written and read see the following:

```
- /principia/         (this folder can be anywhere and called anything)
  - data/             Data folder
  - storage/          User data directory
  - principia         Screenshot build executable
  - principia.state   The state the screenshotter is in (e.g. in progress or resting)
- /tmp/
  - principia.run     Unix pipe, used for IPC and connecting to an existing Principia instance
```

When the screenshot build is launched with no arguments and it finishes loading, it will freeze at the end of the loading screen with a "Ready! o.o" message. In this idle state, it is waiting for a message to be sent over the Unix pipe.

(TODO: Explain more about how it takes screenshots of a level and saves them)

# Uses
The semi-automatic screenshotter script written in Python that ROllerozxa uses to take screenshots for principia-web now uses the screenshot build to take screenshots. It can be found [here](https://github.com/principia-game/level-screenshotter).

There is also a work in progress Docker image for the screenshotter that is meant to be deployed for use on principia-web for completely automatic level screenshotting, available [here](https://github.com/principia-game/screenshotter-container).
