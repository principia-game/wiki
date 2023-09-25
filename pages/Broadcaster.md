{{ infobox_object({
	"id": 125,
	"name": "Broadcaster",
	"category": "Electronics",
	"sublayer_width": 14,
}) }}

Broadcast a signal over a range of frequencies.

If a value other than 0 is receiver through **`IN1`**, the frequency range is shifted by + **`IN1`** * 10 rounded to the nearest whole value.

If multiple broadcasters broadcast over the same frequencies, what value a receiver would pick up is undefined. A transmitter transmitting on a frequency in a broadcasters frequency range will override the broadcast value.

## Socket information
- **`IN0`**: The signal to broadcast
- **`IN1`**: Frequency shift