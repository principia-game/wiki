{{ infobox_object({
	"id": 110,
	"name": "Half-unpack",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Invert a half pack.

```
If IN0 > 0.5:
  OUT0: 0
  OUT1: (IN0-0.5) * 2
else
  OUT0: (IN0) * 2
  OUT1: 0
```
