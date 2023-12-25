The Lua scripting environment contains several callbacks which the game will call at certain points. You can define these callback functions to run code.

## `init()`
A callback that runs once on the initial load of the LuaScript.

First argument `is_sandbox` can be used to check whether the level is played from the sandbox or not (`true`/`false`).

Example:

```lua
function init(is_sandbox)
	game:message("is_sandbox: " .. (is_sandbox and "yes" or "no"))
end
```

## `step()`
A callback that runs on every game step.

First argument `count` is an incrementing counter that increments by one for every step.

```lua
function step(count)
	game:show_numfeed(count)
end
```

## `on_event()`
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

## `on_input()`
A callback that gets called when a key is pressed.

TODO

## `on_response()`
A callback that gets called when a prompt opened with `game:prompt()` is closed with a

Example:

```lua
function on_response(response, prompt_id)
	game:message('The response I got from prompt ' .. prompt_id .. ' was ' .. response)
end
```

## `on_halt()`
Called when the script is halted due to reaching the execution time limit. (?) (TODO)
