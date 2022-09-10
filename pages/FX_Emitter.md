{{ infobox_object({
	"id": 135,
	"name": "FX Emitter",
	"category": "Tools/effects",
	"sublayer_width": 14,
}) }}

Display special effects depending on the values specified in its config menu. The FX Emitter can display four effects simultaneously.

Explosion - An explosion effect, similar to that of the land mine and bomb.
Highlight - Highlights any connected object, depending on the radius and count.
Smoke - Black smoke
Magic - Sparks of magic
Break - A very subtle breaking effect.
Destroy connections - Destroys any already-destructible objects connected to the FX emitter, subject to the Radius and Count variables.

## Socket information:
- **`IN0`**: Activate
- **`OUT0`**: Outputs a 1 when the effects have finished