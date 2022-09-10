{{ infobox_object({
	"id": 45,
	"name": "NAND gate",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

Same as the AND gate, but the output value is inverted.

The NAND gate is a binary device. Given two inputs, **`IN0`** and **`IN1`**, **`OUT0`** will output 1 if at most one of **`IN0`** and **`IN1`** are 1. Since this is a binary device, the input value is rounded so any value above 0.5 is equal to 1.

## Socket information:
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: A NAND B