{{ infobox_object({
	"id": 56,
	"name": "Moving Average",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Output a value according to:

`I := xa + I(1-a)`

Where `x` is the input signal, `I` is the internal value and `a` is a weight factor.

`I` is always initially 0.

**Example usage:**
Connect a Moving Average component to a Floor component, the input value of the system will "charge" for some time depending on the Moving Average's weight factor, before a 1 is output.