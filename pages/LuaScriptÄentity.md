A reference to a Principia object.

## `entity:get_id()`
Added in **1.3**

Returns the unique ID of the current entity.

```lua
entity:get_id()
```

## `entity:get_g_id()`
Added in **1.3**

Returns the type ID of the current entity.

```lua
entity:get_g_id()
```

## `entity:get_position()`
Added in **1.3**

Returns the position of the current entity.

```lua
local x, y = entity:get_position()
```

## `entity:get_angle()`
Added in **1.3**

Returns the angle of the current entity, in radians.

```lua
local angle = entity:get_angle()
```

## `entity:set_angle()`
Added in **1.5.2** (2023-04-21)

Sets the angle of the entity, in radians. Only works on entities that are either completely free or attached to a hinge.

```lua
entity:set_angle(angle)
```

## `entity:get_velocity()`
Added in **1.3**

Returns the linear velocity of the current entity.

```lua
local xvel, yvel = entity:get_velocity()
```

## `entity:get_angular_velocity()`
Added in **1.3**

Returns the angular velocity of the current entity.

```lua
local avel = entity:get_angular_velocity()
```

## `entity:get_bbox()`
Added in **1.3**

Returns the approximate width and height of the object.

```lua
local width, height = entity:get_bbox()
```

## `entity:get_layer()`
Added in **1.4**

Returns the layer of the current entity.

```lua
local layer = entity:get_layer()
```

## `entity:local_to_world()`
Added in **1.4**

Returns the world coordinates converted from the given local coordinates from the current entity.

```lua
local wx, wy = entity:local_to_world(lx, ly)
```

## `entity:world_to_local()`
Added in **1.4**

Returns the local coordinates converted from the given world coordinates in relation to the current entity.

```lua
local lx, ly = entity:world_to_local(wx, wy)
```

## `entity:highlight()`
Added in **1.4**

Highlight the entity.

```lua
entity:highlight()
```

## `entity:damage()`
Added in **1.5**

Only works on destructible objects or creatures.

**NOTE:** Entering a negative amount will heal the object or creature.

```lua
entity:damage(amount)
```

## `entity:is_static()`
Added in **1.5**

Returns true if the entity is a static object (unable to move), otherwise false.

```lua
if entity:is_static() then
    game:message('This entity is static!')
end
```

## `entity:absorb()`
Added in **1.5**

Absorbs the entity if possible. The value returns indicates whether the absorb was completed successfully.

```lua
local success = entity:absorb(follow_connections)
```

## `entity:apply_torque()`
Added in **1.5**

Apply torque to the entity.

```lua
entity:apply_torque(torque)
```

## `entity:set_velocity()`
Added in **1.5**

Sets the linear velocity of the given entity.

```lua
entity:set_velocity(x, y)
```

## `entity:warp()`
Added in **1.5**

Warps the entity to the given x/y world coordinates and layer. If the third argument is unset(layer), the layer will not be changed.

```lua
entity:warp(wx, wy, layer = -1)
```

## `entity:show()`
Added in **1.5**

Shows the entity if it was previously hidden.

```lua
entity:show()
```

## `entity:hide()`
Added in **1.5**

Hides the entity if it was previously visible. It will still interact with the world even though it's hidden.

```lua
entity:hide()
```

## `entity:is_hidden()`
Added in **1.5.2** (2023-04-19)

Returns whether the entity is currently hidden or not.

```lua
local is_hidden = entity:is_hidden()
```

## `entity:get_name()`
Added in **1.5**

Returns the name of the given entity.

```lua
local name = entity:get_name()
```

## `entity:is_creature()`
Added in **1.5**

Returns true if the given entity is a creature.

```lua
if entity:is_creature() then
    game:message(entity:get_name() .. ' is a creature!')
end
```

## `entity:is_robot()`
Added in **1.5**

Returns true if the given entity is any kind of robot.

```lua
if entity:is_robot() then
    game:message(entity:get_name() .. ' is a robot!')
end
```

## `entity:is_player()`
Added in **1.5**

Returns true if the given entity is the current player.

```lua
if entity:is_player() then
    game:message(entity:get_name() .. ' is the current player!')
end
```

## `entity:get_mass()`
Added in **1.5**

Returns the mass of the entity.

```lua
local mass = entity:get_mass()
```

## `entity:get_density()`
Added in **1.5**

Returns the average density of all fixtures of the given entity.

```lua
local density = entity:get_density()
```

## `entity:get_friction()`
Added in **1.5**

Returns the average friction of all fixtures of the given entity.

```lua
local friction = entity:get_friction()
```

## `entity:get_restitution()`
Added in **1.5**

Returns the average restitution of all fixtures of the given entity.

```lua
local restitution = entity:get_restitution()
```

## `entity:set_color()`
Added in **1.5**

Sets the color of the given entity, if possible. Does not work will all entities.

**NOTE:** This function should be used sparingly due to its performance cost, especially when used on pixels.

```lua
entity:set_color(r, g, b)
```

## `entity:disconnect_all()`
Added in **1.5**

Detach all connections from the entity.

```lua
entity:disconnect_all()
```

## `entity:set_target_id()`
Added in **1.5**

Sets the target ID of the given entity. Currently only usable with the robot manager.

```lua
entity:set_target_id(target_id)
```

## `entity:call()`
Added in **1.5**

If the entity is a LuaScript object, call the specified function.

```lua
local x, y = entity:call("my_ultracool_function", a, b, c)
```