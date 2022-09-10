{{ infobox_object({
	"id": 193,
	"name": "Active display",
	"category": "Signal-misc",
	"sublayer_width": 14,
}) }}

Displays a matrix of 5x7 lights forming configurable symbols. By default, the display contains 36 symbols, 0-9 followed by A-Z.

This display is active and updates its current symbol every tick according to the value received through IN1. The input value is a fraction where 0 is the first symbol and 1 is the last symbol.

Symbols can be customized by clicking the configuration button.

## Socket information:
- **`IN0`**: ON/OFF (default ON)
- **`IN1`**: Set symbol
- **`OUT0`**: Current symbol