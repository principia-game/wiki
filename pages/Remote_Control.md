The Remote Control (RC) family of objects are control panels that allow the player to manage contraptions by interacting with widgets that represent an output signal on the RC object.

In custom levels, RC objects with widgets will have a wiggling star icon on them, indicating that they can be pressed to show the RC's widgets. In adventure mode, the adventure robot can attach to nearby RC objects to show the widgets.

To prevent interaction from being necessary to show the widgets of an RC, the [[RC Activator]] can be used to target an RC object which should be automatically activated when starting the level or when an input signal is received.

By default, the camera will snap to RC objects unless an active [[Cam Targeter]] is taking priority. You can disable this with the "Disable RC camera snap" level property.

## Objects
There are the following RC objects available in the game, which vary in size and amount of widgets they support:

- [[RC Micro]]: A tiny RC object with only space for one widget.
- [[RC Basic]]: A simple RC object with space for four widgets.
- [[RC IO-3]]: A more advanced RC object with space for three widgets, as well as additional sockets for each widget for feedback and override functionality.
- [[RC MONSTRO]]: Has the same connectivity as the RC IO-3, but with space for eight widgets.

## Widgets
Each RC object has a different amount of widgets it has space for, corresponding with how many output signals it has. Pressing the configuration button on any RC object will open up the configuration screen where you can drag widgets from the top to the two bottom corners.

The following widgets are available, going from left to right:

{{ image({
	"url": "images/remote_control/rc_widgets.webp",
	"alt": "RC widgets"
}) }}

- Horizontal sliders, coming in 3x1 and 2x1 variants. Left end of the slider is 0.0 and the right end is 1.0, with intermediary positions being a raw value between 0.0 and 1.0.
- Arrow buttons, which have arrow icons and map to WASD on desktop. If your control scheme is in any form directional you should use these instead of the regular buttons, as it will lead to a better experience for keyboard players. Buttons' default value is 0, and when pressed it sends a continuous value of 1 until released. You may want to use a [[Sparsifier]] to convert this into a single click instead.
- Generic buttons, which can be used for any purpose and do not have any specific icon.
- Vertical sliders, coming in 1x3 and 1x2 variants. Bottom end of the slider is 0.0 and the top end is 1.0, with intermediary positions being a raw value between 0.0 and 1.0.
- Radials, coming in 2x2 and 3x3 variants. The signal value goes from 0.0 to 1.0 counter-clockwise, starting from the right-most position. This is the same signal format that [[Servo Motor]]s use.
- Fields, coming in 2x2 and 3x3 variants. These widgets occupy two output sockets, first one denotes the position of the crosshair in the X axis and the second one the Y axis.
- "Clicky" radial, which send signals through two sockets. The first output socket is for the angle of the outer radial knob, while the second output socket is for the button in the center of the widget.

Each RC area is a grid of 3x3 cells, and each widget occupies a certain amount of cells depending on its type. The output socket(s) for each widget is shown in or above the corresponding widget. Sliders, rotaries and field widgets can be dragged in the configuration dialog to set their default value, which will be the value reported by the widget when the level starts. Their default positions always correspond to 0.

{{ image({
	"url": "images/remote_control/rc_widget_grid.webp",
	"alt": "A 3x3 widget grid showing some widgets placed out on OUT0-2"
}) }}

Tip: You can wire up output sockets with a [[Debugger]] or [[Grapher]] to visualise the output values of widgets in real time.
