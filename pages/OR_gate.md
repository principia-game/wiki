{{ infobox_object({
	"id": 43,
	"name": "OR gate",
	"category": "Signal-i2o1",
	"sublayer_width": 14
}) }}

Outputs 1 when at least one of its input is 0.

The OR gate is a binary device. If any input is 1, output 1. Otherwise output 0. Since this is a binary device, the input value is rounded so any value above 0.5 is equal to 1.

Essentially, it acts as a reverse [[Y-splitter]] and can combine two inputs into one.

## Lua implementation
```lua
local in0 = this:read(0)
local in1 = this:read(1)
if in0 >= 0.5 or in1 >= 0.5 then
	this:write(0, 1)
else
	this:write(0, 0)
end
```

## Socket information
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: A OR B
