{{ infobox_object({
	"id": 170,
	"name": "IF-else",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

If binary value of **`IN1`** is 1.0, out the unmodified value of **`IN0`** to **`OUT1`**, else out it to **`OUT0`**.

The input **`IN1`** is binary, its value is rounded so any value above 0.5 is equal to 1.

## Lua implementation
```lua
local in0 = this:read(0)
local in1 = this:read(1)
if in1 >= 0.5 then
	this:write(1, in0)
else
	this:write(0, in0)
end
```

## Socket information
- **`IN0`**: Value
- **`IN1`**: Condition
- **`OUT0`**: `IF NOT IN1 THEN IN0 ELSE 0`
- **`OUT1`**: `IF IN1 THEN IN0 ELSE 0`
