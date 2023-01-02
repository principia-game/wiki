{{ infobox_object({
	"id": 174,
	"name": "SFX Emitter",
	"category": "Tools/effects",
	"sublayer_width": 14,
}) }}

Plays one of the preset sound effects.

In 1.5, the SFX emitter was updated to allow for more sound effects to be used, alongside picking the sound chunk and whether it should loop. The old pre-1.5 selection of sounds still exist in levels with a version lower than 28 (1.5), but upgrading the level will make it play another sound that has the same ID in the new sound list.

## Socket information:
- **`IN0`**: Activate
- **`IN1`**: Volume control