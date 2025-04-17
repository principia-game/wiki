{{ infobox_object({
	"id": 181,
	"name": "Linear Decay",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

Adds any non-zero input value to its internal value. Each tick its internal value is subtracted by the amount given in the on-screen slider.

If **`IN0`** is non-zero, add it to its internal value (`cur_value` += **`IN0`**). Each tick, subtract `cur_value` by the `decay_value` set with the on-screen slider.

The Linear Decay object used to not clamp its values, leading to it being able to output ranges outside of the 0.0-1.0 range. This has since been fixed, but there are still other ways of outputting signals outside of the regular 0.0-1.0 range (see [[Hacked Signals]]).

## Socket information
- **`IN0`**: Set value
- **`OUT0`**: `cur_value`
