{{ infobox_object({
	"id": 75,
	"name": "Proximity sensor",
	"category": "Robotics",
	"sublayer_width": 15
}) }}

Measures the distance to the closest object. The value sent to **`OUT0`** is equal to `1.0-D/L` where `D` is the real distance to the object and `L` is the range of the sensor (see Length slider).

The Proximity Sensor will activate if ANYTHING is in its detection range including immovable objects and world walls.

## Socket information
- **`OUT0`**: Inverted distance according to `1.0-D/L`
