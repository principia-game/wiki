{{ infobox_object({
	"id": 72,
	"name": "Tiltmeter",
	"category": "Robotics",
	"sublayer_width": 15,
}) }}

Output the angular displacement of the Tiltmeter relative to its standing position.

Tiltmeter sensitivity is calculated by dividing the sensitivity setting by 360. At sensitivity 1, the Tiltmeter will reach max 1.0 after a full revolution. Sensitivity 2 = half rotation, 4 = quarter rotation etc.

**Note:** The Tiltmeter remembers its initial position and number of rotations, so if you rotate a Tiltmeter (sens=1) 5 times around during building it will need to rotate back 5 full revolutions to actually function again.

## Socket information
- **`OUT0`**: Counter-clockwise rotation. 0.0 is no rotation, 1.0 is 180 degrees
- **`OUT1`**: Clockwise rotation. 0.0 is no rotation, 1.0 is 180 degrees