{{ infobox_object({
	"id": 200,
	"name": "Robot Factory",
	"category": "Game",
	"sublayer_width": 15,
}) }}

A factory object that can produce robots.

## Socket information:
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