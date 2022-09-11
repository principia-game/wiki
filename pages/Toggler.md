{{ infobox_object({
	"id": 54,
	"name": "Toggler",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Whenever a bit of 1 is read from **`IN0`**, the output stream is toggled.

**Example:** `0001001000010` -> `0001110000011`

A constant stream of ones leads to the toggler switching constantly, so using it in combination with a [[Sparsifier]] is useful for things like wiring it up to an RC button.

## Socket information:
- **`IN0`**: Input signal
- **`OUT0`**: Output of the Toggler's current value