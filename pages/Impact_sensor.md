{{ infobox_object({
	"id": 144,
	"name": "Impact sensor",
	"category": "Robotics",
	"sublayer_width": 15
}) }}

When an impact occurs, for example an object collided with the sensor, a value is sent through **`OUT0`**.

Use the Threshold slider to set the maximum impact value. This will be the value corresponding to 1.0 through **`OUT0`**.

## Socket information
- **`OUT0`**: Impact value between 0.0 and 1.0
