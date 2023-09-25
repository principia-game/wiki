{{ infobox_object({
	"id": 46,
	"name": "Inverter",
	"category": "Signal-i1o1",
	"sublayer_width": 14,
}) }}

Inverts **`IN0`** and outputs it to **`OUT0`**. If the input signal is raw, 1 - **`IN0`** is written to **`OUT0`**.

Essentially, it can be used to turn an 1.0 binary signal into 0.0 and vice versa. With analog raw signals it can be thought as reversing the distance of the input signal from 0.5, 0.4 (-0.1 from 0.5) becomes 0.6 (0.1 from 0.5).

Examples:
```lua
0.0 -> 1.0
1.0 -> 0.0
0.3 -> 0.7
0.5 -> 0.5   -- 0.5 stays the same
```

## Socket information
- **`IN0`**: Input signal
- **`OUT0`**: Inverted **`IN0`**