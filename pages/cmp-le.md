{{ infobox_object({
	"id": 173,
	"name": "cmp-le",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

Short for "Compare lesser or equal". Outputs 1 if the **`IN0`** input value is less than or equal to the **`IN1`** input value, otherwise output 0.

For a non-inclusive comparison, use [[cmp-l]].

## Socket information:
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: IF (A <= B) THEN 1 ELSE 0