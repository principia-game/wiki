`this` is a reference to the unique LuaScript object itself. `this` is a **global** object.

[toc]

## `this:write()`
Added in **1.3**

Writes the value to the given OUT-socket. Values will be clamped between 0.0 and 1.0.

**NOTE:** This should only be called once per step.

```lua
this:write(socket_id, value)
```

## `this:read()`
Added in **1.3**

Reads the value from the given IN-socket.

```lua
local value = this:read(socket_id)
```

## `this:has_plug()`
Added in **1.5**

Returns true if the given IN-socket has a plug attached to it.

```lua
local b = this:has_plug(socket_id)
```

## `this:write_frequency()`
Added in **1.3.0.2**

Writes the value to the given frequency. Values will be clamped between 0.0 and 1.0.

**NOTE:** This should only be called once per step.

```lua
this:write_frequency(frequency, value)
```

## `this:listen_on_frequency()`
Added in **1.4**

Starts listening on the given frequency.**NOTE:** Must be called in the init-function.

```lua
this:listen_on_frequency(frequency)
```

## `this:read_frequency()`
Added in **1.4**

Reads the value from the given frequency.

**NOTE:** this:listen_on_frequency() must have been called for the frequency before this is used.

```lua
local value = this:read_frequency(frequency)
```

## `this:first_run()`
Added in **1.3.0.2**, deprecated since **1.5**

Returns true if the current step is called in the first run.

```lua
if this:first_run() then
	-- do something
end
```

## `this:get_position()`
Added in **1.3.0.2**

Returns the position of the LuaScript object.

```lua
local wx, wy = this:get_position()
```

## `this:get_id()`
Added in **1.5**

Returns the unique ID of the LuaScript object.

```lua
local id = this:get_id()
```

## `this:get_resolution()`
Added in **1.5**

Returns the resolution Principia is currently running at.

```lua
local width, height = this:get_resolution()
```

## `this:get_ratio()`
Added in **1.5**

Returns the current screen ratio as a fraction (`window_width / window_height`).

```lua
local ratio = this:get_ratio()
```

## `this:set_sprite_blending()`
Added in **1.3.0.2**

Sets the current blending mode used for drawing sprites.
- `0` = 0ff
- `1` = Mode A
- `2` = Mode B

```lua
this:set_sprite_blending(blend_mode)
```

## `this:set_sprite_filtering()`
Added in **1.3.0.2**

Sets the current filter mode used for drawing sprites.
- `0` = Nearest
- `1` = Linear

```lua
this:set_sprite_filtering(filter_mode)
```

## `this:set_sprite_texel()`
Added in **1.3.0.2**

Sets the color of a sprite texel.

```lua
this:set_sprite_texel(x, y, r, g, b, a)
```

## `this:clear_texels()`
Added in **1.4**, latest update **1.5**

Clears all texels. From 1.5 it can now take a clear value. (0-255)

```lua
this:clear_texels(clear_value)
```

## `this:set_draw_tint()`
Added in **1.4**

Sets the color for future sprite draws. (was `this:set_sprite_tint` in 1.3.0.2)

```lua
this:set_draw_tint(r, g, b, a)
```

## `this:set_draw_z()`
Added in **1.4**

Sets the Z-value for future sprite draws. (`this:set_sprite_z` in 1.3.0.2)

```lua
this:set_draw_z(z_value)
```

## `this:set_draw_coordinates()`
Added in **1.5**

Sets the coordinate mode any future sprite draws will use.
- `0` = World-based coordinates
- `1` = Screen-based coordinates (0,0 to 100,100)
- `2` = Local-based coordinates (Local to LuaScript-object by default, can be changed with the optional parameter local_id)

```lua
this:set_draw_coordinates(coordinate_mode, local_id)
```

## `this:draw_sprite()`
Added in **1.3.0.2**

Draws a sprite with the given parameters.

```lua
this:draw_sprite(x, y, rotation, width, height, texel_from_x, texel_from_y, texel_to_x, texel_to_y)
```

## `this:draw_line()`
Added in **1.4**

Draws a line with the given parameters.

```lua
this:draw_line(x1, y1, x2, y2, width)
```

## `this:draw_gradient_line()`
Added in **1.5**

Draws a gradient line with the given parameters. The color of the first point will be the one set in `this:set_draw_tint()`, and the second point will be the values given in the function parameters.

```lua
this:draw_gradient_line(x1, y1, x2, y2, width, r, g, b, a)
```

## `this:draw_line_3d()`
Added in **1.5**

Draws a 3d line with the given parameters.

```lua
this:draw_line_3d(x1, y1, z1, x2, y2, z2, width)
```

## `this:draw_gradient_line_3d()`
Added in **1.5**

Draws a 3D gradient line with the given parameters. The color of the first point will be the one set in `this:set_draw_tint()`, and the second point will be the values given in the function parameters.

```lua
this:draw_gradient_line_3d(x1, y1, z1, x2, y2, z2, width, r, g, b, a)
```

## `this:get_sprite_texel()`
Added in **1.5**

Returns the color for the given sprite texel.

```lua
local r, g, b, a = this:get_sprite_texel(x, y)
```

## `this:init_draw()`
Added in **1.5**

Initializes the drawing functionality for the current LuaScript object with the width and height specified.

- Minimum width or height: 1
- Maximum width or height: 1024
- Width and height MUST be a power-of-two. (i.e. 1, 2, 4, ..., 32, 64, 128, 256, 512, 1024)

```lua
this:init_draw(width, height)
```

## `this:set_static_sprite_texel()`
Added in **1.5**

Sets the color of a static sprite texel. X and Y must be within 0 and the (width/height)-1 specified in `this:init_draw()`.

```lua
this:set_static_sprite_texel(x, y, r, g, b, a)
```

## `this:clear_static_texels()`
Added in **1.5**

Clears all static texels to the given color. If no colors are specified, `0x7F` will be set for all channels.

```lua
this:clear_static_texels(r, g, b, a)
```

## `this:add_static_sprite()`
Added in **1.5**

Adds a sprite to be rendered with the given parameters. This only needs to be called once per sprite, because it will persist until this:clear_static_sprites() is called.

```lua
this:add_static_sprite(x, y, rotation, width, height, texel_from_x, texel_from_y, texel_to_x, texel_to_y)
```

## `this:clear_static_sprites()`
Added in **1.5**

Removes all sprites that have been previously added with `this:add_static_sprite()`.

```lua
this:clear_static_sprites()
```
