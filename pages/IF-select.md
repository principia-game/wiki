{{ infobox_object({
	"id": 218,
	"name": "IF-select",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Like a ternary operator, outputs the value of **`IN1`** if `IN2 >= 0.5`, else output the value of **`IN0`**

## Socket information
- **`IN0`**: Value
- **`IN1`**: Value
- **`IN2`**: Conditional
- **`OUT0`**: `Conditional ? IN1 : IN0`
