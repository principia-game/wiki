{{ infobox_object({
	"id": 158,
	"name": "Ceil",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

If the input value is anything other than exactly 0, output 1.

Any raw signal other than exactly 0.0 is treated as 1.0. For example, 0.00001 is treated as 1.0.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Result of a ceil operation to **`IN0`**
