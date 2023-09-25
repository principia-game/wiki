{{ infobox_object({
	"id": 44,
	"name": "AND gate",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

Outputs 1 when both of its inputs are 1.

The AND gate is a binary device. If both **`IN0`** and **`IN1`** is 1, output 1. Otherwise output 0. Since this is a binary device, the input value is rounded so any value above 0.5 is equal to 1.

## Lua implementation
```lua
local in0 = this:read(0)
local in1 = this:read(1)
if in0 >= 0.5 and in1 >= 0.5 then
	this:write(0, 1)
else
	this:write(0, 0)
end
```

## Socket information
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: A AND B