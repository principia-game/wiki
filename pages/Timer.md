{{ infobox_object({
	"id": 87,
	"name": "Timer",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

A timer ticks a value of 1.0 at a a defined interval, for a specified number of times. Click the configuration button to set how many times and at what interval the timer should tick.

Send a single value of 1.0 to **`IN1`** to reset the timer, or a continuous stream of 1 to stop it.

## Socket information
- **`IN0`**: Start (default = on)
- **`IN1`**: Stop/Reset
- **`OUT0`**: Timer tick
- **`OUT1`**: Timer status (1.0 if the timer is stopped or was reset)
