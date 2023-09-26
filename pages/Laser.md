{{ infobox_object({
	"id": 71,
	"name": "Laser",
	"category": "Robotics",
	"sublayer_width": 15
}) }}

A device that emits light at the given wavelength. If the wavelength is set above 0, it will damage robots with an increasing damage amount depending on the wavelength.

The laser beam can be bounced and directed using a [[Laser bouncer]]. To detect if something crosses the laser beam, place a [[Laser sensor]] to receive the beam.

## Socket information
- **`IN0`**: Activate, by default 1.0 if no cable is connected