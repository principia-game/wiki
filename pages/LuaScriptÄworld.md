World functions. world is a **global** object.

## `world:get_entity()`
Added in **1.3**, Latest update **1.5**.

Returns an entity (object) reference or `nil` if the object does not exist. `entity_id` refers to the object's unique ID, **not** the g_id which is the same for each type of object.

Renamed from `world:get_entity_by_id()` in 1.5.

```lua
local my_entity = world:get_entity(entity_id)
```

## `world:raycast()`
Added in **1.4**

Raycasts from start to end. Returns nil if nothing was hit, otherwise returns the entity, ptx, pty, norx, nory.

```lua
local entity, ptx, pty, norx, nory = world:raycast(startx, starty, endx, endy, layer)
```

## `world:query()`
Added in **1.4**

Returns a table of entities located within the given coordinates. Layers and sublayers are optional arguments.

```lua
local entities = world:query(min_x, min_y, max_x, max_y, layer, sublayers)
```

## `world:get_gravity()`
Added in **1.4**

Returns the current X and Y gravity of the world.

```lua
local x, y = world:get_gravity()
```

## `world:set_gravity()`
Added in **1.5.2** (2023-04-19)

Set the gravity of the world.

```lua
world:set_gravity(x, y)
```

## `world:get_adventure_id()`
Added in **1.5**

Returns the ID that belongs to the Adventure Robot, if it exists.

```lua
local id = world:get_adventure_id()
```

## `world:get_borders()`
Added in **1.5**

Returns the border sizes of the world.

```lua
local bup, bdown, bleft, bright = world:get_borders()
```

## `world:get_world_point()`
Added in **1.5**

Converts a global screen point to a world point.

```lua
local wx, wy = world:get_world_point(gsx, gsy)
```

## `world:set_bg_color()`
Added in **1.5**

Sets the background color to the given values.

**NOTE:** Only works if you're using a colored background in the first place.

```lua
world:set_bg_color(r, g, b)
```

## `world:set_ambient_light()`
Added in **1.5**

Sets the ambient light of the world to the given value.

```lua
world:set_ambient_light(intensity)
```

## `world:set_diffuse_light()`
Added in **1.5**

Sets the diffuse light of the world to the given value.

```lua
world:set_diffuse_light(intensity)
```