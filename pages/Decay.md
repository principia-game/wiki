{{ infobox_object({
	"id": 164,
	"name": "Decay",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

Adds any non-zero input value to its internal value. Each tick its internal value is multiplied by the amount given in the on-screen slider.

If **`IN0`** is non-zero, add it to its internal value (`cur_value` += **`IN0`**). Each tick, multiply `cur_value` by the `decay_rate` set with the on-screen slider. `cur_value` is clamped between 0 and 1.

## Socket information
- **`IN0`**: Set value
- **`OUT0`**: `cur_value`