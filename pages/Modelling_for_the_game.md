This page contains notes on making 3D models for the game.

To preface, it is worth noting that the game's asset and data pipeline is rather primitive and adding new content that would entail new models will also mean making code changes. However these instructions are intended to also be useful for 3D modellers without C++ programming knowledge, who want to contribute models that can be implemented into the game.

## Modelling software and formats
The recommended software to use is [Blender](https://www.blender.org/), which is free and open source and available for both Windows and Linux. It is also what has historically been used for the game's development going back to its proprietary roots, and source `.blend` files for all models in the game should be available in the [data-src directory in the source repository](https://github.com/Bithack/principia/tree/master/data-src). These are useful for reference as well as for if you are making a model that is similar to something that already exists in the game.

The model format that the game uses is `.3ds`, also referred to as the Autodesk 3D Studio format (Note that it is not a proprietary format, and you do not need Autodesk software to use it!). This format is generally considered to be legacy nowadays, but is a simple format for 3D models and can still be exported from software such as Blender.

While older versions of Blender shipped with an exporter add-on built-in which you may need to enable in Preferences -> Add-ons, in Blender 4.1 and onwards you need to install the [Autodesk 3D Studio (.3ds)](https://extensions.blender.org/add-ons/autodesk-3ds-format/?utm_source=blender-5.1.2) extension separately. However this can be conveniently done from the Get Extensions tab in the Blender preferences dialog.

## Materials and textures
The game's asset pipeline is rather primitive and things such as materials and textures are defined in code rather than in data files such as the model itself. While you can apply a material in Blender to see how it looks, this will not reflect into the game unless you make code changes to the game. Materials for the game are defined in `material.cc`, which can have shaders and textures as well as physical properties attached to them for the physics simulation.

Sockets for electronic devices are also defined in code and if you are making a model, it is important to put the sockets at a predictable distance from eachother as this will make the implementation easier, as well as being aesthetically pleasing.

## Testing models in-game
It is important to be able to test your models in-game as early as possible to see that you're not doing something that the game can't handle. To do this, you can replace a model in the game that is similar to the one you're making.

It is recommended to use a separate portable version of the game you can afford to mess around with when editing the game's data files. For Windows you can use the portable build, while on Linux it may be most convenient to build from source and then do `touch portable.txt` in the build directory to turn the game portable.

By default the game will cache model data in a `models.cache` file. In order to disable this, you can set the following setting in `settings.ini` to 1 which will always make it read the raw models from disk:

```
always_reload_data=1
```

Then you can go into `data/models/` and replace a given model with your own, and it should take effect once you have restarted the game.
