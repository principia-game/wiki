The way code is executed in the LuaScript object was hugely reworked in 1.5 along with an extension of the API, making use of callback functions to determine what to run on init as well as on each tick.

Newly created levels will always use the currently latest level version at the time, and will use the new way of executing code. If you open old pre-1.5 levels from the archive in the sandbox, it will use the old way of executing code, even if you add a new LuaScript object and save the level. **The old execution model is only kept for compatibility with new levels. When writing new code, you should always be using the new model.**

## Checking the level version
If you create a LuaScript object on an old level version, it will contain this message advising you to upgrade the level version:

```lua
-- This is a new LuaScript object created in a level version below 1.5.
-- It will not support modern LuaScript functionality such as the init()
-- and step() callbacks. To use modern LuaScript please upgrade the level
-- to the latest version.
```

You can see what level version a level uses in the Level Properties dialog, and can upgrade it to the latest version if it is not already the latest.

{{ image({
	"url": "/wiki/images/luascript/level_version.webp",
	"alt": "Level version: 1.4.0.2 - upgrade to latest (2023-06-05)"
}) }}

Do note that upgrading an existing level may make other things behave in different ways, see [[Level Versions]] for a list of changes in each version.

## Old execution model vs new
In the old execution model, everything written outside of a function gets called every step. To run something on the first step you would use the `this:first_run()` method to check for the first tick and put any init code inside an if block.

```lua
local count

if this:first_run() then
	game:message("This runs only once!")
	count = 0
end

-- Runs every step
count = count + 1
game:show_numfeed(count)
```

When using the new execution model, the code above is rewritten into this:

```lua
local count = 0

function init()
	game:message("This runs only once!")
end

function step()
	count = count + 1
	game:show_numfeed(count)
end
```

The `init` callback runs on the first step and should contain what was previously gated by `this:first_run()`. For simple variable definitions, these can be written on the same line outside of any function scope. Any other code that you want to run on each step should be put into the `step` callback.

This is also more in line with other API features implemented in 1.5 and beyond which also make use of callbacks to run code on certain events. See [[LuaScript/Callbacks]] for a list of additional callback functions which the API uses.
