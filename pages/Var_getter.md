{{ infobox_object({
	"id": 176,
	"name": "Var getter",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Retrieve an analog signal value associated with the specified name. These variables are persistent between playthroughs and stored in a cache file associated with the level.

The configuration dialog is used to set the name of the variable used. The dialog also has buttons to reset the value of the current variable, or to reset all variables for the level.

You can also retrieve Principia variables using the `game:get_variable(varname)` method in Lua.

To set a value, see the [[Var setter]].

## Socket information
- **`OUT0`**: Value
