The interface system allows you to connect motors to CT objects with a single cable, while providing it both power and signal information in both ways. This allows for better control and feedback of motors, while keeping your electronics organised.

{{ image({
	"url": "images/interface_system/dc_vs_simple_motor.webp",
	"alt": "Top part shows a Simple Motor wired up directly to a Power Supply and an RC Basic, while the bottom part shows a DC Motor wired up to a CT Mini. The CT Mini is then wired up to a Power Supply and an RC Basic.",
	"caption": "Example of the difference in wiring between the Simple Motor (top) and the DC Motor (bottom)."
}) }}

[[Interface Cable]]s are blue and have significantly wider plugs. There is no way to run interface signals wirelessly, but the [[Interface Clip]] can be used for cable management.

## Interface objects
- [[DC Motor]]: A regular motor with an interface socket.
- [[Servo Motor]]: A motor that can be controlled to rotate to a specific angle.
- [[Linear Motor]]: A linear motor that moves along a straight line.
- [[Linear Servo]]: A linear motor that can be controlled to move to a specific position.

## CT Objects
All CT objects have an interface socket and power socket on them.

- [[CT Mini]] contains a speed control and reverse socket.
- [[CT Servo]] contains a control socket for servo objects, and two feedback sockets.
- [[CT Feedback]] contains the same input sockets as the CT Mini, but also has three feedback sockets.
