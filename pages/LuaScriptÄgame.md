A global object containing various *game*-stuff. game is a **global** object.

[toc]

## `game:show_numfeed()`
Added in **1.3**, Latest update **1.3.0.3**

Shows the given number on the screen for debugging.

From **1.3.0.3** and onward, it can take a `num_decimals` argument which specifies with what precision the number should be printed.

```lua
local x, y = game:show_numfeed(number, num_decimals)
```

## `game:finish()`
Added in **1.3.0.2**

Finish the game with the desired win state:
- `1` = win
- `0` = lose

```lua
game:finish(win_state)
```

## `game:add_score()`
Added in **1.3.0.2**

Modifies the current score. Use a negative number to decrease the score.

```lua
game:add_score(score_mod)
```

## `game:set_score()`
Added in **1.3.0.2**

Sets the current score.

```lua
game:set_score(new_score)
```

## `game:get_score()`
Added in **1.3.0.2**

Returns the current score.

```lua
local score = game:get_score()
```

## `game:activate_rc()`
Added in **1.3.0.2**

Activate RC Control of an entity using its object fetched with world:get_entity().

```lua
game:activate_rc(world:get_entity(entity_id))
```

## `game:activate_rc_by_id()`
Added in **1.3.0.2**

Activate RC Control of an entity using its ID.

```lua
game:activate_rc_by_id(entity_id)
```

## `game:message()`
Added in **1.4**

Outputs a toast message on the screen. Duration:
- `0` = Short
- `1` = Long

```lua
game:message(message, duration)
```

## `game:get_cursor()`
Added in **1.4**

Gets the world coordinates for the cursor in the given layer.

```lua
local wx, wy = game:get_cursor(layer)
```

## `game:poll_event()`
Added in **1.4**

Returns true if the given event just occurred. See [[Event Listener]] for event IDs.

**NOTE:** This function should not be used any longer, and will be deprecated soon. Instead, use the on_event function.

```lua
game:poll_event(event_id)
```

## `game:get_screen_cursor()`
Added in **1.5**

Get the cursor position on the screen. (Screen-based coordinates, based on the users screen resolution)

```lua
local x, y = game:get_screen_cursor()
```

## `game:restart()`
Added in **1.5**

Restart the level.

```lua
game:restart()
```

## `game:submit_score()`
Added in **1.5**

Submits the player last saved score.

**NOTE**: If the score is submitted before the level has been finished (by game over of level completed), the current score will not be saved yet.

```lua
game:submit_score()
```

## `game:set_variable()`
Added in **1.5**

Sets the value of the given Principia variable.

**NOTE**: Variables from Lua can contain values outside the normal 0.0-1.0 scope.

```lua
game:set_variable(varname, value)
```

## `game:get_variable()`
Added in **1.5**

Gets the value of a variable.

**NOTE**: Variables from Lua can contain values outside the normal 0.0-1.0 scope.

```lua
local value = game:get_variable(varname)
```

## `game:get_fps()`
Added in **1.5**

Returns the average FPS.

```lua
local fps = game:get_fps()
```

## `game:prompt()`
Added in **1.5.1**

Opens a [[Prompt]] with the given parameters.

Returns the ID of the prompt dialog that was created, which can be used for verification purposes. Returns nil if no prompt was created.To get the response, implement the following function:

```lua
function on_response(response, prompt_id)
	game:message('The response I got from prompt ' .. prompt_id .. ' was ' .. response)
end
```

The response function will only be called once, store the value if you wish.

Valid responses:
- `1` = First button.
- `2` = Second button.
- `3` = Third button.

```lua
local prompt_id = game:prompt("Do you want to do something?", "Yes", "No", "Maybe!")
```
