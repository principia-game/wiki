{{ infobox_object({
	"id": 196,
	"name": "Robot Manager",
	"category": "Game",
	"sublayer_width": 14,
}) }}

Controls or outputs information about the selected robot.

## Socket information
- **`IN0`**: God mode ON/OFF.
- **`IN1`**: Speed modifier (0.0-1.0). Only enabled if the cable is plugged in. A value of 0.0 means the robot is unable to walk.
- **`IN2`**: Disable action (useful for disabling box mode until certain power up is enabled).
- **`IN3`**: Jump strength multiplier.
- **`IN4`**: HP increase (heal), value * 10
- **`IN5`**: HP decrease (damage), value * 10
- **`IN6`**: Max HP increase, value * 10
- **`IN7`**: Max HP decrease, value * 10
- **`IN8`**: Weapon damage multiplier 0.0 = No extra damage, 1.0 = 5 times the damage.
- **`IN9`**: Toggle robot action.
- **`IN10`**: Walk left.
- **`IN11`**: Walk right.
- **`IN12`**: Stop all movement.
- **`IN13`**: Jump.
- **`IN14`**: Aim.
- **`IN15`**: Attack.
- **`IN16`**: Attach to nearest backpack/RC
- **`IN17`**: Detach from any backpack/RC
- **`IN18`**: Respawn
- **`IN19`**: Freeze
- **`IN20`**: Toggle roaming (non-adventure robots only).
- **`IN21`**: Cycle weapons
- **`IN22`**: Cycle factions
- **`OUT0`**: Weapon arm angle
- **`OUT1`**: Tool arm angle
- **`OUT2`**: On weapon fire
- **`OUT3`**: On tool use (experimental)
- **`OUT4`**: Current layer. 0.0 = layer 1, 0.5 = layer 2, 1.0 = layer 3
- **`OUT5`**: Head removed
- **`OUT6`**: Moving left - User attempting to move left (adventure robot only)
- **`OUT7`**: Moving right - User attempting to move right (adventure robot only)
- **`OUT8`**: Look dir (left = 0.0, right = 1.0)
- **`OUT9`**: dir - Last movement dir (left = 0.0, right = 1.0)
- **`OUT10`**: Action active
- **`OUT11`**: 1.0 if attached to anything, otherwise 0
- **`OUT12`**: Movement left feedback (adventure robot only)
- **`OUT13`**: Movement right feedback (adventure robot only)
- **`OUT14`**: jump feedback (adventure robot only)
- **`OUT15`**: aim feedback (adventure robot only)
- **`OUT16`**: layer up feedback (adventure robot only)
- **`OUT17`**: layer down feedback (adventure robot only)
- **`OUT18`**: action feedback (adventure robot only)