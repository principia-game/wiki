{{ infobox_object({
	"id": 175,
	"name": "Synthesizer",
	"category": "Tools/effects",
	"sublayer_width": 14
}) }}

An electronic device which creates sounds based on its settings and electronic inputs.

## Configuration
* **Base frequency** - The frequency at which the synthesizer will emit its sound.
* **Peak frequency** - The highest frequency at which the synthesizer can emit its sound. This is only relevant when **`IN1`** is used.
* **Waveform** - How the emitted sound will oscillate
	* **Sine Wave**
	* **Square Wave** - Great for percussive instruments
	* **Pulse Wave** - Same as square wave, but with a customisable width
	* **Sawtooth** - Great for string and brass sounds
	* **Triangle Wave**
* **Pulse width** - (Only used with the Pulse Wave) Specifies the width of the pulse. The width of a square wave is 0.5 (50%) for reference.
* **Bitcrushing** - Produces a distortion effect by reducing the resolution of the sound.
* **Frequency vibrato Hz** - Specifies at what speed the frequency vibrato should be applied.
* **Frequency vibrato extent** - To what extent the frequency should vibrate.
	Assuming a base frequency of 220, a Frequency Vibrato Extent of 0.1 will make the sound vibrate between `220 - (220 * 0.1)` and `220 + (220 * 0.1)`.
* **Volume vibrato Hz** - Specifies at what speed the volume vibrato should be applied.
* **Volume vibrato extent** - How much the volume will shift.

## Socket information
- **`IN0`**: Volume (1.0 by default)
- **`IN1`**: Frequency shift. (base frequency + (peak frequency - base frequency) * **`IN1`**)
