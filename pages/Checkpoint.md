{{ infobox_object({
	"id": 140,
	"name": "Checkpoint",
	"category": "Game",
	"sublayer_width": 15
}) }}

An adventure mode object. If the **`IN0`** receives a signal &ge;0.5, this checkpoint is activated. This means if and when the Adventure robot is killed, this is the Checkpoint on which the robot will respawn. The checkpoint can also be activated by having the Adventure robot stepping on it.

## Socket information
- **`IN0`**: Activate
- **`OUT0`**: Outputs a single 1 if the robot respawns on this checkpoint
- **`OUT1`**: Active status. Outputs 1 if this is the current checkpoint in use
