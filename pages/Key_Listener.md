{{ infobox_object({
	"id": 216,
	"name": "Key Listener",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Detects and outputs a signal when a key is held down, resetting when it is released. Click the configuration button to select a key.

You can use a [[Sparsifier]] to get a single signal for detecting when it is pressed, and [[Sparsifier+]] to get both when it's pressed and released.

## Socket information
- **`OUT0`**: Outputs a constant signal when the selected key is pressed
