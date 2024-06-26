{{ infobox_object({
	"id": 34,
	"name": "Signal Cable",
	"category": "Electronics",
	"sublayer_width": 15
}) }}

Cable used for signaling. Signals can be any value between 0 and 1. Many signals are either 0 (off) or 1 (on), and are then called binary signals. When a signal is any other fraction between 0 and 1, such as 0.5, then the signal is referred to as a "raw" signal.

Some devices only care for binary signals, these devices are called binary devices. Examples of binary devices include the [[XOR gate]], [[AND gate]] and [[Sparsifier]]. When a raw signal is sent to a binary device, the signal is rounded to the nearest binary number. For example, a value of 0.75 would be rounded to 1, and a value of 0.123 would be rounded to 0. A value of 0.5 is rounded upwards to 1.

All devices operate at a frequency of 125 Hz, which means 125 signals can be sent through your whole circuitry each second.
