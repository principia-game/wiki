{{ infobox_object({
	"id": 160,
	"name": "Cursor finder",
	"category": "Interaction",
	"sublayer_width": 14,
}) }}

Outputs the angle and distance to the cursor, or if on a mobile device, to the first finger that's pressed down on the screen. The angle and distance are saved, so it can be used as a "last touch position" for mobile devices.

## Socket information
- **`OUT0`**: Angle
- **`OUT1`**: Distance