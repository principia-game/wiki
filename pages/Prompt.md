{{ infobox_object({
	"id": 167,
	"name": "Prompt",
	"category": "Interaction",
	"sublayer_width": 14,
}) }}

Upon receiving a signal of 1 to **`IN0`**, a customizable dialog will be shown to the player. Use the configuration dialog to specify the text and of the dialog. Use the output sockets to receive signals for which option the user selected.

The output sockets will send a constant stream unless the prompt has been displayed again and another option is selected, so a [[Sparsifier]] is recommended if you want only one single signal.

## Socket information:
- **`IN0`**: Activate. It's recommended to use [[Limit]] or [[Sparsifier]] to this input.
- **`OUT0-2`**: Button 1-3 pressed last time it was displayed