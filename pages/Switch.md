{{ infobox_object({
	"id": 38,
	"name": "Switch",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

The input signal (**`IN0`**) is sent to any of the 5 outputs. Initially, the signal is sent to **`OUT0`**. The **`IN1`** and **`IN2`** switch which output receives the signal. If a 1 is sent to **`IN2`**, the next output is selected, if a 1 is sent to **`IN1`**, the previous output is selected.

A [[Sparsifier]] can help filter out abundant data.

## Socket information
- **`IN0`** Input signal to send through the switch
- **`IN1`** Switch to lower output
- **`IN2`** Switch to higher output
- **`OUT0-5`** Output switches