{{ infobox_object({
	"id": 57,
	"name": "0-Reset M. Avg",
	"category": "Signal-i1o1",
	"sublayer_width": 14
}) }}

Identical to [[Moving Average]], but immediately resets itself when an input signal of exactly 0 is received:

```
I: = / x > 0 : xa + I(1-a)
     \ x = 0 : 0
```

Where `x` is the input signal, `I` is the internal value and `a` is a weight factor.

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Resulting output value
