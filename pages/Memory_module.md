{{ infobox_object({
	"id": 103,
	"name": "Memory module",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

Stores a value in its buffer which is output to **`OUT0`**. The value is read from **`IN1`**, and a signal from **`IN0`** sets the buffer value to the value read from **`IN0`**.

## Socket information
- **`IN0`**: Set, a signal above 0.5 sets the buffer value to the **`IN1`** value.
- **`IN1`**: Input, the value which will be stored in the buffer if **`IN0`** is true.
- **`OUT0`**: The buffer value