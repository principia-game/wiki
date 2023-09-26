{{ infobox_object({
	"id": 166,
	"name": "Time Ctrl",
	"category": "Tools/effects",
	"sublayer_width": 14
}) }}

**NOTE: This is a beta object, please be careful when using it as it can have unintended behaviour.**

Slow down time according to the input value.

Time can NOT be stopped completely since that would stop all electronics from running and prevent you from starting time again. An epsilon value of 0.01 is added as the minimum time speed.

## Socket information
- **`IN0`**: Multiply time speed by (1.0-**`IN0`**) + `EPS`