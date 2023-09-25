{{ infobox_object({
	"id": 219,
	"name": "Cam Rotator",
	"category": "Signal-misc",
	"sublayer_width": 14,
}) }}

Rotate the camera to the angle of **`IN1`** if **`IN0`** is above 0.5.

Default for **`IN0`** is 0 so a [[Jumper]] may be necessary if you want the rotator to be active at all times.

## Socket information
- **`IN0`**: Set camera angle (Default to 0)
- **`IN1`**: Camera angle value