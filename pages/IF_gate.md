{{ infobox_object({
	"id": 79,
	"name": "IF gate",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

If binary value of **`IN1`** is 1.0, out the unmodified value of **`IN0`** to **`OUT0`**.

The input **`IN1`** is binary, its value is rounded so any value above 0.5 is equal to 1.

## Lua implementation
```lua
local in0 = this:read(0)
if in0 >= 0.5 then
	this:write(0, in0)
else
	this:write(0, 0)
end
```

## Socket information
- **`IN0`**: Value
- **`IN1`**: Condition
- **`OUT0`**: `IF IN1 THEN IN0 ELSE 0`