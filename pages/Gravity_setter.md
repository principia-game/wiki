{{ infobox_object({
	"id": 105,
	"name": "Gravity setter",
	"category": "Tools/effects",
	"sublayer_width": 15
}) }}

Use the on-screen sliders to specify what the gravity should be set to. Only one gravity setter should be active at the same time, otherwise the gravity will be undefined.

A cable needs to be plugged into the gravity setter and output a non-zero value to be activated. For example:

Sending a signal of 0.5 to the Gravity setter will set the gravity to the values set with the on-screen sliders, and halve them. (0, -20 with 0.5 multiplier would result in 0, -10 gravity)

## Socket information
- **`IN0`**: Gravity multiplier
