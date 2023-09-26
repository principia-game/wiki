{{ infobox_object({
	"id": 182,
	"name": "Limit",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

An electronic device that can be used to limit how many ticks of 1 can be passed through it.

Useful for limiting how many times things like a [[Prompt]] can be activated.

Since this is a binary device, the input value is rounded so any value above 0.5 is equal to 1.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Limited output signal