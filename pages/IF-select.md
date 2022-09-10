{{ infobox_object({
	"id": 218,
	"name": "IF-select",
	"category": "Signal-misc",
	"sublayer_width": 14,
}) }}

Outputs the value of **`IN0`**if **`IN2`** is less than 0.5, otherwise output the value of IN1.

## Socket information:
- **`IN0`**: Value
- **`IN1`**: Value
- **`IN2`**: Conditional
- **`OUT0`**: `Conditional ? IN1 : IN1`