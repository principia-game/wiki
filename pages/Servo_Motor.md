{{ infobox_object({
	"id": 21,
	"name": "Servo Motor",
	"category": "Robotics",
	"sublayer_width": 7,
}) }}

A motor that is good for precise angle control or abrupt speed control. Power this motor by connecting it to a controller (CT) using an [[Interface Cable]] (blue cable).

Characteristics:
* Low maximum speed
* High torque
* A desired speed below the current speed slows down (brakes) the motor
* Applies torque to hold its idle position or desired angle

By default, the 0-angle is set to the initial angle of the motor. The pink rotary icon can be used to adjust the initial offset to the 0-angle. For example, if you align the pink rotary icon with what you have connected to the motor, the offset will return the 0-angle to point right. For absolute angle control, you should always align the pink rotary icon with what you have connected.

## Socket information
- **`IN0`**: Interface socket