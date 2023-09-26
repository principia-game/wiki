{{ infobox_object({
	"id": 188,
	"name": "Factory",
	"category": "Game",
	"sublayer_width": 15
}) }}

This is where the adventure robot can create things in game. When the Factory is clicked, a menu pops up where you can select what objects to build.

Most objects require oil, see the Oil Rig.

## Socket information
- **`IN0`**: Add to queue
- **`IN1`**: What to build
- **`IN2`**: Absorb items without interaction
- **`IN3`**: Conveyor ON/OFF
- **`IN4`**: Conveyor invert direction
- **`OUT0`**: Something was emitted
- **`OUT1`**: Something was absorbed
- **`OUT2`**: Error (not enough material)
- **`OUT3`**: Current build progress
- **`OUT4`**: Binary, if something is building