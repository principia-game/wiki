Procedural terrain is a level feature that can generate infinite 2D terrain featuring vegetation, robot hideouts and deep caves.

You can create a level with procedural terrain by choosing "Procedural adventure" in the "Create new level" menu, which will place down a robot in the procedural terrain world. Note that Procedural adventure is not a level type in itself, and if you do not want an adventure robot you can simply change the level type to Custom in the level properties dialog.

The procedural terrain was originally implemented as part of the [[Exploration Mode]] to create a more interesting and dynamic world for the player to explore. While this mode has been removed, the procedural terrain generator is still available to be used in the sandbox and will not be removed.

## The terrain
The terrain consists of four different types of voxel-like blocks which look like the [[Block]] object, but cannot be manipulated like regular objects in the sandbox. To manipulate the terrain in the sandbox you can use the [[Terrain Paint]] mode.

The terrain generator has a basic concept of biomes and the amount of grass will vary across the world with a "Tundra factor". The higher the tundra factor the more exposed stone will be present in the terrain, while a lower tundra factor will result in more grass and vegetation.

## Vegetation
On grassy ground, the terrain generator will place down various types of plants. The following will spawn with some randomness:

- Tree: A regular tree (what you'd get when placing down a [[Plant]] in the sandbox)
- Bush: A small plant consisting primarily of leaves and a small trunk
- Colorful Bush: A bush with pink (cherry blossom-like) leaves
- Big tree: A larger tree with a thicker trunk and more leaves
- Sand tree: A tree with very circular tree crowns
- Rough tree: A tree with a likelihood of growing crooked with less leaves

In addition to plants, random stone decorations are also placed down on the surface of the terrain in the same vegetation step.

## Features
This is a list of special terrain generation "features" which denote any kind of more complex detail of the terrain that can randomly be placed down while generating new terrain.

- Enemies: Clusters of enemy robots of various types on the surface
- Animals: Clusters of [[Animal]]s of various ages.
- Hole: A small ravine-like hole in the ground.
- Hidden factory: A small underground structure guarded by enemy robots containing one kind of factory (either [[Factory]], [[Robot Factory]], [[Armory]], [[Oil Mixer]]).
- Minerals: Clusters of ores which can be mined for [[Resource]]s.
- Cave: An underground structure with cave systems containing enemy robots as well as [[Treasure Chest]]s with loot inside.
- Deep cave: A larger cave system that spawns deeper underground, with more enemy robots and [[Treasure Chest]]s where the quality of the loot increases the deeper they spawn.
- Grave: A small structure sitting on top of the ground which contains Pioneer parts ([[Pioneer front]], [[Pioneer back]]) inside.
