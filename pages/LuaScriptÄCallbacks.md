The Lua scripting environment contains several callbacks which the game will call at certain points. You can define these callback functions to run code.

[toc]

## `init(is_sandbox)`
A callback that runs once on the initial load of the LuaScript.

First argument `is_sandbox` can be used to check whether the level is played from the sandbox or not (`true`/`false`).

Example:

```lua
function init(is_sandbox)
	game:message("is_sandbox: " .. (is_sandbox and "yes" or "no"))
end
```

## `step(count)`
A callback that runs on every game step.

First argument `count` is an incrementing counter that increments by one for every step.

```lua
function step(count)
	game:show_numfeed(count)
end
```

## `on_event(id)`
A callback that gets called whenever an event occurs.

First argument `id` is the event ID.

Example:

```lua
function on_event(id)
	if id == EVENT_ENEMY_ID then
		game:message("Enemy robot just died!")
	end
end
```

## `on_input(type, data)`
A callback that gets called when a key is pressed.

The first argument is the input type ID. The following IDs exist, which have respective constants defined:

| ID  | Constant           |
| --- | ------------------ |
| 4   | INPUT_KEY_DOWN     |
| 8   | INPUT_KEY_UP       |
| 16  | INPUT_POINTER_DOWN |
| 32  | INPUT_POINTER_UP   |

The second argument is a table containing some data which depends on the input ID.

**For keys:**

One key called `keycode` which contains a keycode of the pressed key. While TMS' keycodes include more than those below, these are the most common keys that also have helper constants provided:

| ID  | Constant      |
| --- | ------------- |
| 4   | KEY_A         |
| 5   | KEY_B         |
| 6   | KEY_C         |
| 7   | KEY_D         |
| 8   | KEY_E         |
| 9   | KEY_F         |
| 10  | KEY_G         |
| 11  | KEY_H         |
| 12  | KEY_I         |
| 13  | KEY_J         |
| 14  | KEY_K         |
| 15  | KEY_L         |
| 16  | KEY_M         |
| 17  | KEY_N         |
| 18  | KEY_O         |
| 19  | KEY_P         |
| 20  | KEY_Q         |
| 21  | KEY_R         |
| 22  | KEY_S         |
| 23  | KEY_T         |
| 24  | KEY_U         |
| 25  | KEY_V         |
| 26  | KEY_W         |
| 27  | KEY_X         |
| 28  | KEY_Y         |
| 29  | KEY_Z         |
| 30  | KEY_1         |
| 31  | KEY_2         |
| 32  | KEY_3         |
| 33  | KEY_4         |
| 34  | KEY_5         |
| 35  | KEY_6         |
| 36  | KEY_7         |
| 37  | KEY_8         |
| 38  | KEY_9         |
| 39  | KEY_0         |
| 40  | KEY_ENTER     |
| 41  | KEY_ESC       |
| 42  | KEY_BACKSPACE |
| 43  | KEY_TAB       |
| 44  | KEY_SPACE     |
| 79  | KEY_RIGHT     |
| 80  | KEY_LEFT      |
| 81  | KEY_DOWN      |
| 82  | KEY_UP        |

**For pointer input (i.e. mouse click, finger press):**

A table with three keys is provided:

- `pid`: The ID of the pointer.
	- On desktop the primary mouse button is mapped to 0, secondary mouse button is mapped to 1 and the scrollwheel button is mapped to 2.
	- On mobile each finger touching the screen is given an increasing ID.
- `x`: X position where the input happened in the native windows resolution and with origin in the bottom left.
- `y`: Y position where the input happened in the native windows resolution and with origin in the bottom left.

Example:

```lua
function on_input(id, data)
	if id == INPUT_KEY_DOWN then
		if data.keycode == KEY_F then
			game:message("You just paid your respects.")
		end
	elseif id == INPUT_POINTER_DOWN then
		game:message("You pressed the screen at ("..data.x..","..data.y..")!")
	end
end
```

## `on_response(response, prompt_id)`
A callback that gets called when a prompt opened with `game:prompt()` is closed with a button being pressed.

Example:

```lua
function on_response(response, prompt_id)
	game:message('The response I got from prompt ' .. prompt_id .. ' was ' .. response)
end
```

## `on_halt()`
Called when the script is halted due to reaching the execution time limit.
