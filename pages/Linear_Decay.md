{{ infobox_object({
	"id": 181,
	"name": "Linear Decay",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Adds any non-zero input value to its internal value. Each tick its internal value is subtracted by the amount given in the on-screen slider.

If **`IN0`** is non-zero, add it to its internal value (`cur_value` += **`IN0`**). Each tick, subtract `cur_value` by the `decay_value` set with the on-screen slider.

The Linear Decay object does not clamp its value, a glitch which leads to it being able to output negative values when IN0 is 0, the value being negative of whatever decay value is set ([Example level](/level/551)). For more information about signals outside the regular range see [[Hacked Signals]].

## Socket information:
- **`IN0`**: Set value
- **`OUT0`**: `cur_value`