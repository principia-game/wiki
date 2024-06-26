{{ infobox_object({
	"id": 157,
	"name": "Passive display",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Displays a matrix of 5x7 lights forming configurable symbols. The current symbol pointer can be increased and decreased using **`IN1`** and **`IN2`**. **`IN0`** controls whether the display is on or off. By default if no cable is connected to **`IN0`**, the display is on. By default, the display contains 36 symbols, 0-9 followed by A-Z.

Prior to 1.4 the passive display was known as the Digital display.

Symbols can be customized by clicking the configuration button.

## Socket information
- **`IN0`**: ON/OFF (default ON)
- **`IN1`**: Increment symbol pointer
- **`IN2`**: Decrement symbol pointer
