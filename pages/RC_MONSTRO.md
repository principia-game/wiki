{{ infobox_object({
	"id": 29,
	"name": "RC MONSTRO",
	"category": "Robotics",
	"sublayer_width": 14,
}) }}

Control panel with support for 8 widgets, capable of overriding signals and receiving feedback from external electronics.

Each widget is connected to 2 output slots and 3 input slots, i.e. any widget 'x' is connected to **`OUTx`**, **`OUT(x+8)`**, **`INx`**, **`IN(x+8)`** and **`IN(x+16)`**.

* **`OUT0-7`**
Raw signal, same as any other RC object. If override mode is enabled, the override value is reported here instead.

* **`OUT8-15`**
Reports widget focus. For example, if a slider is dragged and held at 0, the raw signal is 0, but the focus signal is 1. When the slider is released the raw signal remains at 0 and the focus signal turns 0 as well. This can be used to create a recoil effect, when the focus value is 0, send a 1 (inverted focus signal) to the **`IN16-23`** (Override enabled/disabled), when the slider is released it will recoil back to 0 (or another value as set through **`IN8-15`**).

For a button, the focus signal is always equal to the raw signal, unless the raw signal is overridden (see below).

* **`IN0-7`**
Feedback input. Report the current value of the widget here. The current value will be displayed as a visual hint on screen. For example, a button will light up as if pressed, and a slider will show an extra knob at the feedback position. Can be used to, for example, create a toggle button (scroll down to see examples).

* **`IN8-15`**
Set the override-value. The value received here is the alternative output value used when override mode is enabled (see below).

* **`IN16-23`**
Toggles override-mode and selects which output signal to use. A binary value of 0 means the control panel output value is used (from widgets on the screen), and a binary value of 1 means the widget is ignored and the value is overridden and read from **`IN8-15`** instead.

## Examples
### 1) Toggle button
We want a button that each time pressed changes its state. We want the state to be reflected on the visible button. Add a button widget to **`OUT0`**, and connect **`OUT0`** to a [[Sparsifier]]. Then connect the [[Sparsifier]] to a [[Toggler]]. The output of the [[Toggler]] is the value we want. Send the toggler output to **`IN0`** (feedback value) and also your own electronics. You now have a toggle button.

### 2) Slider with recoil
Add a slider widget to **`OUT0`**. Connect **`OUT8`** (focus) to an [[Inverter]] and then to **`IN16`** (Override enable/disable). The slider will now recoil to 0 when not focused (inverted focus value = 1), if you want it to recoil to another value than 0, for example 0.5, then connect something to **`IN8`** (Set value). 0 is the default value for override if nothing is connected.

### 3) Slider with springy recoil
We want to create a slider with a recoil effect that acts like a spring and does not instantly go back to 0. Add a slider widget to **`OUT0`**. Connect **`OUT8`** (focus) to an [[Inverter]] and then to **`IN16`** (Override enable/disable). Connect **`OUT0`** (raw signal) to your own electronics and separately to a [[Square]] component. Connect the [[Square]] component to **`IN8`** (Override value).

## Socket information
- **`OUT0-7`** Raw signal
- **`OUT8-15`** Focus signal (0 or 1)
- **`IN0-7`** Feedback/report current value
- **`IN8-15`** Override value
- **`IN16-23`** Override enabled/disabled