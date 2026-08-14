{{ infobox_object({
	"id": 27,
	"name": "RC Basic",
	"category": "Robotics",
	"sublayer_width": 14
}) }}

Basic control panel with support for 4 output signals.

The RC family of objects allows you to construct control interfaces with buttons, sliders and rotary widgets. These widgets send signals (through red wires), that you can process and forward to your own electronics.

Click the configuration button to open up the control panel configuration screen. Drag widgets to place them on the screen. Each widget will be connected to an output socket, the first widget you place will be connected to **`OUT0`**, the second to **`OUT1`**, and so on.

See [[Remote Control]] for a detailed description of how remote control panels work.

## Socket information
- **`OUT0-4`**: Raw signal from the configured widget
