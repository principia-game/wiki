{{ infobox_object({
	"id": 54,
	"name": "Toggler",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Whenever a bit of 1 is read from **`IN0`**, the output stream is toggled.

**Example:**
`0001001000010` -> `0001110000011`

Use in combination with the sparsifier and the effect on control panel buttons is a "checkbox" that can be toggled on/off.