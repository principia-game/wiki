{{ infobox_object({
	"id": 220,
	"name": "Level Manager",
	"category": "Game",
	"sublayer_width": 14
}) }}

Set the light intensity of your level.

These values can also be changed in [[LuaScript]] using the `world:set_ambient_light` and `world:set_diffuse_light` functions, passing the given intensity to each.

## Socket information
- **`IN0`**: Set ambient to value of IN1
- **`IN1`**: Ambient value
- **`IN2`**: Set diffuse to value of IN3
- **`IN3`**: Diffuse value
