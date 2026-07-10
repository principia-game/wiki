{{ infobox_object({
	"id": 177,
	"name": "Var setter",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Store a value and associate it with a name. These variables are persistent between playthroughs and stored in a cache file associated with the level.

The configuration dialog is used to set the name of the variable used. The dialog also has buttons to reset the value of the current variable, or to reset all variables for the level.

You can also set Principia variables using the `game:set_variable(varname, value)` method in Lua, but the range of the value still needs to be within 0.0-1.0.

To retrieve the value, see the [[Var getter]].

## Socket information
- **`IN0`**: Set
- **`IN1`**: Value
