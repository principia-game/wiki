{{ infobox_object({
	"id": 50,
	"name": "Sparsifier",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

One of the most important devices to understand!

Outputs 1 if **`IN0`** is 1 and the preceding value of **`IN0`** was not 1.

**Example:**
`000011110000` -> `000010000000`

Use this gate to, for example, convert control panel button presses to button "clicks".

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Sparsified output signal