{{ infobox_object({
	"id": 115,
	"name": "Object field",
	"category": "Robotics",
	"sublayer_width": 6
}) }}

Detects an object of a specific type. All objects of the target type will be detected by the field. When an object of the target type enters the field, 1.0 is reported through **`OUT0`**, otherwise 0.0 is reported.

Use the crosshair button to select an object. For example, select a metal ball and all metal balls will trigger the object field. The object field ignores properties such as the size of cylinders.

## Socket information
- **`OUT0`**: Detection status
