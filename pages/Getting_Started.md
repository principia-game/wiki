This page will help you get started in the sandbox. For more tutorials and help resources, check out the rest of the [Principia Wiki](/wiki/).

**(TODO: This thing should preferably be rewritten or repurposed)**

## Power cable system (white cables)
The white cables are used to send electric power to devices requiring it. Examples of objects that need power include the Fan, Trampoline (optional), and all the CT (controller) objects. Currently you can choose from two power sources: Battery (3V) and Power Supply (custom voltage). The power supply is voltage and current regulating so each output is independent of the others - a selected voltage of 24 will output 24 V to all connected cables.

## Signal system (red cables)

The signal system is very simple, but one of the most advanced areas of Principia. This is the kind of cable you will spend most time with. A value sent through the cable can be anything between 0.0 and 1.0. Here are some examples of what some objects output:

- A button outputs 0 until it is pressed, then it outputs 1.0
- The tiltmeter will output a value closer to 1 the more tilted it is.
- The proximity sensor will measure the distance to the nearest object and output the distance as one minus a fraction of its maximum reach

You can use the Debugger device to test the output of any object. The debugger will light up brighter and brighter the closer to 1.0 its input value is.

### Fundamental objects

#### [[Sparsifier]]
The Sparsifier is probably the most important object to know. In short, it converts a long signal to a "click".

For example, a button will normally output 1's infinitely after it has been pressed. Connect it through a sparsifier and the result will be a single "click" when the button is pressed, followed by infinite 0's. Maybe it doesn't sound very useful, but you'll learn soon that the sparsifier will be useful in almost all of your builds.

#### Debugger
It helps to visualize the current value passing through the signal, use the debugger for this purpose.

## Interface system (blue cables)

The interface system can be found between motors of various kinds and Controllers ("CT").  A controller will pack a bunch of signal information and electric power and pass it to a motor through a single cable. The purpose of this is to have all your electronics in one place while still being able to do advanced communication with motors (such as getting feedback from and controlling the motor).

## How To...

### Increase/decrease the score
Use the Game Manager object. It has several slots for controlling the current score. Remember to add sparsifiers in front of the slots!

### Define how a level is completed
A level is completed when any of the following conditions are met:

- Level type is Puzzle and any robot steps on the Goal pad.
- Level type is Adventure and the player robot steps on the Goal pad.
- The final score is reached (unless the final score is 0).
- A value greater than 0.5 is sent to a Game Manager's WIN-input socket.

To set up your own rules, all you need to do is connect your electronics to the WIN-input on a game manager and define when the game is won.

### Detect mouse clicks and get mouse position
To detect mouse clicks, use the Event Listener object and choose the Mouse Click or Mouse Release event.
You can not get the absolute mouse position, but you can get the relative position (an angle and a distance) using the Cursor Finder object. Please note that the angle is relative to the Cursor Finder itself.

### Detect an object

There are many ways to detect objects. Here are some options:

- ID Field - Detects a specific unique object of your choice
- Object field - Detects any object of a specific type. For example, detect all cylinders, all robots or all wooden balls.
- Proximity sensor - Reports the distance to the nearest object (of any type).
- Laser + Laser sensor - Detect when the laser beam is interrupted.
- Pressure sensor - Detect if something heavy is lying on the sensor or if the sensor was hit hard.
- Impact sensor - Detect collisions
- Object Finder - reports the relative angle and distance to another unique object.

### Build a simple car
To build a simple car that drives forward automatically, you will need wheels, a few planks, a Simple Motor, a battery, and a power cable.

### Add on-screen buttons and other widgets

In the Robotics category in the sandbox menu you will find a bunch of objects with RC in their name (RC Micro, RC Basic, RC IO-3, and more). An RC is an object that allows you to add buttons on the screen, and connect these buttons to your signaling electronics.


To demonstrate, let us create a simple button that activates a debugger. Start by adding an RC Basic to your level. Choose the Configure-button to open up the RC Edit Mode. Now drag one of the buttons available down to an open slot, either on the left or the right of the screen. When released, you should see which socket it will output its signal through. The first button you add will always output its signal to OUT0. Add a signal cable and a debugger to your level, connect one end of the cable to OUT0 of the RC Basic, and the other end to IN0 of your debugger. Now press play and you will see a star icon over the RC, click on the star to activate the RC. You should see a button, and when you press it the debugger will light up.

### Activate an RC automatically when the level is played

This can be accomplished using the RC Activator object, found under the Game category in the sandbox menu. Place an RC Activator in your level, while having it selected choose the Crosshair-button and select which RC the activator will activate. By default the RC will be activated immediately, but you can activate it on demand by connecting a signal cable to the RC activator and sending a value of 1.0 when it should be activated.

### Let the camera follow an object
The Cam Targeter object can be used to set what object. First, find the Cam Targeter under the "Game" category in the sandbox menu. Place it in your level. Click on the Crosshair-icon and the game will ask you to select an object. Click on an object you would like for the camera to follow.

The Cam Targeter will be automatically enabled when the game is started. You can activate it on demand by connecting a signal cable to it and sending a value of 1.0.
