{{ infobox_object({
	"id": 176,
	"name": "Var getter",
	"category": "Signal-misc",
	"sublayer_width": 14,
}) }}

Retrieve a value associated with the specified name. These variables are persistent between playthroughs and stored in a cache file associated with the level. Use the config dialog to set the variable name, or to reset the variable's value.

You can also retrieve Principia variables using the `game:get_variable(varname)` method in Lua.

To set a value, see the [[Var setter]].

## Socket information:
- **`OUT0`**: Value