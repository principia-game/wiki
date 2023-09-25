{{ infobox_object({
	"id": 56,
	"name": "Moving Average",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Linearly interpolates the signal.

The output value is calculated according to `I := xa + I(1-a)`, where `x` is the input signal, `I` is the internal value and `a` is a weight factor configurable with the Coefficient property. `I` is always initially 0.

## Examples

* Connect a Moving Average component to a [[Floor]] component, the input value of the system will "charge" for some time depending on the Moving Average's weight factor, before a 1 is output.

* Set up an RC with a circle widget, and wire it up to a [[Cam Rotator]] with a Moving Average in the middle. The camera rotation will "lag behind", leading to a smoother rotation than without.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Resulting output value