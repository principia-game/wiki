{{ infobox_object({
	"id": 47,
	"name": "Floor",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

If the input value is anything other than exactly 1, output 0.

Any raw signal other than exactly 1.0 is treated as 0.0. For example, 0.99999999 is treated as 0.0. It basically discards the fractional part of a raw signal.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Result of a floor operation to **`IN0`**