{{ infobox_object({
	"id": 42,
	"name": "XOR gate",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

Outputs 1 when exactly one of its input is 1.

The XOR gate is a binary device. If a value of 1 is read from **`IN0`** or **`IN1`**, but not from both at the same time, the XOR gate outputs 1. Otherwise it outputs 0. Since this is a binary device, the input value is rounded so any value above 0.5 is equal to 1.

## Socket information:
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: A XOR B