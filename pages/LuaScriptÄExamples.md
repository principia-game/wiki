This page contains small example programs for working with Lua in Principia. Each example is well-commented, and document the prerequisites for what you will need to do in-game to prepare the program if applicable.

The examples focus on working with the LuaScript API more than working with the Lua language itself, but may also be used to get a feel for the syntax of Lua.

[toc]

## Hello World
A simple Hello World program for Principia.

```lua
-- Runs on level start
function init()
	-- Shows a toast message in-game
	game:message("Hello World!")
end
```

## Numfeed
The "numfeed" is a value that is displayed on the top center of the screen. It is useful for debugging as you can send any value to it.

**Prerequisites:** Wire up IN0 of the LuaScript to OUT0 of any RC object such as an [[RC Basic]] and add a slider widget to it.

```lua
-- Runs on each game tick
function step()
	-- Read value from IN0
	local value = this:read(0)

	-- Show the value in the numfeed
	game:show_numfeed(value)
end
```

## Object information
Program that prints the position and velocity information of an object.

**Prerequisites:** After you have added a LuaScript to the level (assumed to be ID 1), add another object. It can be anything, but it will get the ID of 2.

```lua
-- Get an object with the unique ID 2
local obj = world:get_entity(2)

-- Run on each game tick
function step(count)
	-- Get X and Y position of object
	local x, y = obj:get_position()
	-- Get X and Y velocity of object
	local xvel, yvel = obj:get_velocity()

	-- string.format formats a string with placeholder values you pass as
	-- additional arguments to the function.
	-- "%.2f" means to display it as a float with two decimals precision.
	local msg = string.format("Object ID 2 is at (%.2f,%.2f), current velocity (%.2f,%.2f)",
		x, y, xvel, yvel)

	-- Show the formatted message as a toast
	game:message(msg)
end
```

## Sum
Program that sums up all the input signals of the LuaScript object and outputs it to OUT0.

**Prerequisites:** Wire up all inputs of a LuaScript to an RC object such as the [[RC Basic]] and add four slider widgets to it. You would also want to add a [[Grapher]] attached to the LuaScript's OUT0 to display the output value.

```lua
-- Run on each game tick
function step()
	-- Initialise a value to store the sum value
	local sum = 0

	-- Iterate 0,1,2,3 (IN0,IN1,IN2,IN3)
	for i = 0, 3 do
		-- Add the value from the current input into 'sum'
		sum = sum + this:read(i)
	end

	-- this:write automatically clamps values between 0.0-1.0, but othewise
	-- you would do 'sum = math.min(sum, 1)' to prevent an overflow.

	-- To make the output wrap instead, you can use 'sum = sum % 1' with the
	-- modulo operator. Try it!

	-- Write out the sum value to OUT0
	this:write(0, sum)
end
```
