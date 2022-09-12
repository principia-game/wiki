{{ infobox_object({
	"id": 64,
	"name": "Command pad",
	"category": "Game",
	"sublayer_width": 15,
}) }}

When a robot steps on the command pad, it will receive and obey the given message.

## Available commands:
- **`Stop`**: Stops the robot.
- **`Start/Stop toggle`**: If **`IN0`** is connected and is **`0`**, stop the robot. If **`IN0`** is **`1`**, start the robot. By default it will toggle the robots current start or stop value.
- **`Left`**: Changes the robots direction to **left**.
- **`Right`**: Changes the robots direction to **right**.
- **`Left/Right toggle`**: Toggles the robot direction.
- **`Jump`**: Commands the robot to jump. Slider sets with what strength the robot jumps.
- **`Aim`**: Commands the robot to aim its weapon in the specified angle.
- **`Attack`**: Commands the robot to attack.
- **`Layer up`**: Commands the robot to move one layer up.
- **`Layer down`**: Commands the robot to move one layer down.
- **`Increase speed`**: Commands the robot to increase its speed depending on the slider value.
- **`Decrease speed`**: Commands the robot to decrease its speed depending on the slider value.
- **`Set speed`**: Sets the robots speed depending on the slider value.
- **`Full health`**: Gives the robot full health. Has the same texture as the Goal object, which might make the player confuse it with a [[Goal]] object.

## Socket information:
- **`IN0`** Activate (by default on)