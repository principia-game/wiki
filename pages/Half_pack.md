{{ infobox_object({
	"id": 111,
	"name": "Half pack",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Pack two mutually exclusive values, for example a positive and a negative X value, or the output of a Tiltmeter, into a single value.

```
OUT0 = / IN1 > 0 : 0.5 + IN1*.5
       \ IN1 = 0 : IN0*.5
```
