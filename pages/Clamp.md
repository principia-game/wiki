{{ infobox_object({
	"id": 53,
	"name": "Clamp",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

Clamp the input signal to a given minimum and maximum value, inclusive.

To invert the clamp, set the maximum to a lower value than the minimum, the input signal will then be clamped outside of the range.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Clamped value (`Min <= IN0 <= Max`)
