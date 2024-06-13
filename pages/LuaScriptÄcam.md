Controls the player's camera. cam is a **global** object.

[toc]

## `cam:get_position()`
Added in **1.3**

Returns the X, Y and Z coordinates of the camera.

```lua
local x, y, z = cam:get_position()
```

## `cam:get_velocity()`
Added in **1.3**

Returns the X, Y and Z velocity of the camera.

```lua
local x, y, z = cam:get_velocity()
```

## `cam:set_position()`
Added in **1.3**

Sets the position of the camera.

```lua
cam:set_position(x, y, z)
```

## `cam:set_velocity()`
Added in **1.3**

Sets the velocity of the camera.

```lua
cam:set_velocity(x, y, z)
```

## `cam:follow_entity()`
Added in **1.3**

Tells the game to follow the entity using the given properties.

```lua
cam:follow_entity(world:get_entity(entity_id), do_snap, preserve_position)
```

## `cam:follow_entity_by_id()`
Added in **1.3**

Tells the game to follow the entity using the given properties.

```lua
cam:follow_entity_by_id(entity_id, do_snap, preserve_position)
```

## `cam:get_zoom_ratio()`
Added in **1.5**

Returns the fraction of the players current zoom. 0.0 being fully zoomed in, 1.0 fully zoomed out.

```lua
local frac = cam:get_zoom_ratio()
```
