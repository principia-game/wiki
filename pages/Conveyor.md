{{ infobox_object({
	"id": 90,
	"name": "Conveyor",
	"category": "Mechanics",
	"sublayer_width": 15,
	"stationary": "Configurable"
}) }}

A conveyor which will move any objects resting on top of it according to the speed of the conveyor. When not stationary, it can also move itself in the *same* direction as it moves other objects.

The default speed is configurable using the Speed slider. Positive values will move objects on the conveyor to the right, while negative values will move them to the left. `IN1` can invert this direction when passed a binary signal of 1.

## Socket information
- **`IN0`**: Speed multiplier
- **`IN1`**: Invert direction
