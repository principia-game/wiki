{{ infobox_object({
	"id": 52,
	"name": "Epsilon",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Add a very small value (`1e-5`) to the input signal before passing it on. Use this component for systems where the output value does not converge to the output limit. For example, a series of [[sqrt]] components will never reach exactly 1, but the [[Floor]] component requires a value of exactly 1 to output 1. In that case the Epsilon can be useful.

Note that raw signals will never go above 1.0 or below 0.0, and does not wrap around.

## Socket information:
- **`IN0`**: Input signal
- **`OUT0`**: Output with `1e-5` added to the signal