{{ infobox_object({
	"id": 100,
	"name": "sincos",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Converts an angle via **`IN0`** to one positive y-value, one positive x-value, one negative y-value, and one negative x-value;

An angle signal is a value between 0 and 1 where 0.5 corresponds to 180 degrees.

## Socket information
- **`IN0`**: Angle, the angle which will be converted to four x/y-values
- **`OUT0`**: Positive Y
- **`OUT1`**: Positive X
- **`OUT2`**: Negative Y
- **`OUT3`**: Negative X
