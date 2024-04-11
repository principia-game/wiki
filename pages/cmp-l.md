{{ infobox_object({
	"id": 172,
	"name": "cmp-l",
	"category": "Signal-i2o1",
	"sublayer_width": 14
}) }}

Short for "Compare lesser" Outputs 1 if the **`IN0`** input value is less than the **`IN1`** input value, otherwise output 0.

For an inclusive comparison, use [[cmp-le]] which also outputs true when it is equal.

## Socket information
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: IF (A < B) THEN 1 ELSE 0
