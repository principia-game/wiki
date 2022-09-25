{{ infobox_object({
	"id": 65,
	"name": "Goal",
	"category": "Game",
	"sublayer_width": 15,
	"stationary": "Yes"
}) }}

Basic goal for the robot. When any robot steps on the goal, the level is won.

If you only want a particular robot to make the level won, you would need to use an [[ID field]] and create a goal-like platform yourself.

See the [[Game Manager]] if you would like to create a points-based system instead.

## Sockets
- **`IN0`**: Activate the goal (Default is 1)