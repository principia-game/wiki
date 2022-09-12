{{ infobox_object({
	"id": 214,
	"name": "Player Activator",
	"category": "Interaction",
	"sublayer_width": 14,
}) }}

Sets the target as player when receiving a signal. Click the crosshair button to set a target as player.

Only works in adventure mode, and if the player previously already controls a robot (e.g. the adventure robot) it loses control of that robot.

This object works with any kind of robot, allowing the player to control enemy robots and animals, with their own different behaviours.

## Socket information:
- **`IN0`**: Activate (Default 0.0)
- **`OUT0`**: Output status