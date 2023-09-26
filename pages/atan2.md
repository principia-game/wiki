{{ infobox_object({
	"id": 112,
	"name": "atan2",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Converts one positive y-value, one positive x-value, one negative y-value, and one negative x-value to an angle which is output to **`OUT0`**.

An angle signal is a value between 0 and 1 where 0.5 corresponds to 180 degrees.

## Socket information
- **`IN0`**: Positive Y
- **`IN1`**: Positive X
- **`IN2`**: Negative Y
- **`IN3`**: Negative X
- **`OUT0`**: Angle