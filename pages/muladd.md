{{ infobox_object({
	"id": 119,
	"name": "muladd",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

Combined multiply and add. Useful for scaling the signal window to a specific floating point range. For example, multiply by 0.5 and add 0.25 to scale the signal window to a value between 0.25 and 0.75.

`OUT0 = IN0 * a + b`

Set **`a`** and **`b`** using the on-screen sliders.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Resulting output value
