{{ infobox_object({
	"id": 146,
	"name": "HP Control",
	"category": "Signal-misc",
	"sublayer_width": 14,
}) }}

Controls the HP of a robot.

The robots current HP can be read from **`OUT0`**. To set the HP of a robot, set **`IN0`** to 1.0 and **`IN1`** to the desired HP percentage.

## Socket information
- **`IN0:`** Activate
- **`IN1:`** New HP
- **`OUT0:`** Current HP