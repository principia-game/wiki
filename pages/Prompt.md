{{ infobox_object({
	"id": 167,
	"name": "Prompt",
	"category": "Interaction",
	"sublayer_width": 14,
}) }}

Upon receiving a signal of 1 to **`IN0`**, a customizable dialog will be shown to the player. Use the config dialog to specify the details of the dialog. Use the output sockets to receive signals for which option the user selected.

## Socket information:
- **`IN0`**: Activate. It's recommended to use limit or sparsifier to this input.
- **`OUT0`**: Button 1 pressed
- **`OUT1`**: Button 2 pressed
- **`OUT2`**: Button 3 pressed