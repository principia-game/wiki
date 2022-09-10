{{ infobox_object({
	"id": 134,
	"name": "Condenser",
	"category": "Signal-i2o1",
	"sublayer_width": 14,
}) }}

Stores an internal value of the sum of all previous values read from IN0, minus all previous values read from IN1. The internal value is then divided by the maximum value and written to **`OUT0`** as a fraction.

This object can be used as a "health meter". Use **`IN1`** to decrement the health, and **`IN0`** to increment. Wire **`OUT0`** to a ceil device and whenever the result is 0.0, all health is gone.