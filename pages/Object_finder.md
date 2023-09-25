{{ infobox_object({
	"id": 98,
	"name": "Object finder",
	"category": "Robotics",
	"sublayer_width": 14,
}) }}

The object finder locates a specific object. Use the crosshair button to select which object the object finder is tracking.

Please note that the reported angle is the relative angle. If the object finder itself is rotated, the reported angle is with respect to the angle of the object finder. You can use a [[Gyroscope]] and [[Wrap sub]]/[[Wrap add]] to convert between relative/absolute angles.

## Socket information
- **`OUT0`**: Angle
- **`OUT1`**: Distance fraction