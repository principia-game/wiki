{{ infobox_object({
	"id": 20,
	"name": "DC Motor",
	"category": "Robotics",
	"sublayer_width": 7
}) }}

It is a DC motor. Power this motor by connecting it to a controller (CT) using an [[Interface Cable]] (blue cable). For more information on how to use motors, see the [[CT Mini]]. Any side of the motor can be attached to nearby objects.

Characteristics:
- High maximum speed
- Speed control with constant torque
- No engine braking

**NOTE:** Since this motor is not capable of keeping its idle position or slowing down, it might oscillate if interfacing with a [[CT Servo]]. For precise angle control, the [[Servo Motor]] should be used instead.

## Socket information
- **`IN0`**: Interface socket
