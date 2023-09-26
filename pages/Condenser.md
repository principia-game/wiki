{{ infobox_object({
	"id": 134,
	"name": "Condenser",
	"category": "Signal-i2o1",
	"sublayer_width": 14
}) }}

Stores an internal value of the sum of all previous values read from IN0, minus all previous values read from IN1. The internal value is then divided by the maximum value and written to **`OUT0`** as a fraction.

This object can be used as a "health meter". Use **`IN1`** to decrement the health, and **`IN0`** to increment. Wire **`OUT0`** to a [[Ceil]] device and whenever the result is 0.0, all health is gone.

It can also be used for keeping track of a value between 1-20 (or even more with level hacking), as an alternative to the [[Switch]] for more than 5 switch branches. Simply calculate the fraction for each position as `position / Max value` and check against a [[Jumper]] of that value with a [[cmp-e]] or the like. See [32-bit Controllable Binary Counter](/level/8) for an example of this, which uses a hacked condenser that goes all the way up to 32.

## Socket information
- **`IN0`**: Increment
- **`IN1`**: Decrement
- **`OUT0`**: Fraction of stored internal value divided by Max value