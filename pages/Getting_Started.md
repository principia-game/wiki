This page will help you get started in the sandbox. For more tutorials and help resources, check out the rest of the [Principia Wiki](/wiki/).

## Cables
The game contains three different types of cables. Starting out the first two are the most important: white cables are used for sending electric power while red cables are used for sending signals. The third type are blue interface cables and are used for more advanced contraptions featuring CT objects.

### Power cable system (white cables)
The white cables are used to send electric power to devices requiring it. Examples of objects that need power include the [[Simple Motor]], [[Fan]], [[Trampoline]] (optional), and all the CT (controller) objects.

Currently you can choose from two power sources: [[Battery (3V)]] and [[Power Supply]] (custom voltage). Both produce an infinite supply of power, and all outputs in the Power Supply will output the given voltage it is configured to.

### Signal system (red cables)
The signal system is conceptually very simple, but one of the most advanced areas of Principia. This is the kind of cable you will spend most time with. A value sent through the cable can be anything between 0.0 and 1.0. A signal can either be described as a binary signal or an analog signal. Binary signals are either 0.0 or 1.0, with standard rounding logic applying for values in between. Analog signals can be any value between 0.0 and 1.

Here are some examples of what some objects output:

- Binary signal: A [[Button]] outputs 0.0 until it is pressed, then it outputs 1.0.
- Binary signal: An [[OR gate]] will output 1.0 if any of its inputs are 1.0 (actually &ge;0.5), otherwise it will output 0.0.
- Analog signal: The [[Tiltmeter]] will output a value closer to 1 the more tilted it is. (analog signal)
- Analog signal: The [[Proximity sensor]] will measure the distance to the nearest object and output the distance as one minus a fraction of its maximum reach.

You can use a [[Debugger]] or [[Grapher]] to see the signal output of any object.

There are a lot of useful objects in the Signal-i1o1 and Signal-i2o1 categories for working with signals. The [[Sparsifier]] is probably the most important object to know that you will get a lot of use out of. In short, it converts a long signal to a "click".

For example, a button will normally output 1's infinitely after it has been pressed. Connect it through a sparsifier and the result will be a single "click" when the button is pressed, followed by infinite 0's. Maybe it doesn't sound very useful, but you'll learn soon that the sparsifier will be useful in almost all of your builds.

### Interface system (blue cables)
The interface system can be found between motors of various kinds and Controllers ("CT"). A controller will pack a bunch of signal information and electric power and pass it to a motor through a single cable. The purpose of this is to have all your electronics in one place while still being able to do advanced communication with motors (such as getting feedback from and controlling the motor).

## How To...

### Increase/decrease the score
Use the [[Game Manager]] object. It has several slots for controlling the current score. Remember to add [[Sparsifier]]s in front of the slots, unless you want the player to rack up a lot of score!

### Define how a level is completed
A level is completed when any of the following conditions are met:

- Level type is Puzzle and any robot steps on the Goal pad.
- Level type is Adventure and the player robot steps on the Goal pad.
- The final score level property is reached (unless the final score is 0).
- A value &ge;0.5 is sent to a [[Game Manager]]'s WIN-input socket.

To set up your own rules, all you need to do is connect your electronics to the WIN-input on a [[Game Manager]] and define when the game is won.

### Detect mouse clicks and get mouse position
To detect mouse clicks, use the [[Event Listener]] object and choose the Mouse Click or Mouse Release event.

You can not get the absolute mouse position, but you can get the relative position (an angle and a distance) using the [[Cursor finder]] object. Please note that the angle is relative to the [[Cursor finder]] itself.

### Detect an object

There are many ways to detect objects. Here are some options:

- [[ID field]] - Detects a specific unique object of your choice.
- [[Object field]] - Detects any object of a specific type. For example, detect all cylinders, all robots or all wooden balls.
- [[Proximity sensor]] - Reports the distance to the nearest object (of any type).
- [[Laser]] + [[Laser sensor]] - Detect when the laser beam is interrupted.
- [[Pressure sensor]] - Detects if something heavy is lying on the sensor or if the sensor was hit hard.
- [[Impact sensor]] - Detects direct collisions.
- [[Object finder]] - Reports the relative angle and distance to another unique object.

### Build a simple car
To build a simple car that drives forward automatically, you will need [[Wheel]]s, a few planks, a [[Simple Motor]], a [[Battery (3V)]], and a power cable. Then connect the motor to an RC object (such as [[RC Basic]]) to control it. See [Example: Simple Motor](https://principia-web.se/archive/level/378) for a minimal example of a simple controllable car.

For building more advanced vehicles it would be useful to use the CT (controller) objects. See the [Building a Vehicle](/wiki/Building_a_Vehicle_Part_1) tutorial series for more information.

### Add on-screen buttons and other widgets
In the Robotics category in the sandbox menu you will find a bunch of objects with RC (remote control) in their name: [[RC Micro]], [[RC Basic]], [[RC IO-3]] and [[RC MONSTRO]]. An RC is an object that allows you to add buttons on the screen, and connect these buttons to your signaling electronics.

To demonstrate, let us create a simple button that activates a debugger.

1. Start by adding an RC Basic to your level and press the configure (cogwheel) button to open up the RC Edit Mode.
2. Now drag one of the buttons available down to an open slot, either on the left or the right of the screen.
3. When released, you should see which socket it will output its signal through. The first button you add will always output its signal to **`OUT0`**.
4. Add a signal cable and a debugger to your level, connect one end of the cable to **`OUT0`** of the RC Basic, and the other end to **`IN0`** of your debugger.
5. Now press play and you will see a star icon over the RC, click on the star to activate the RC.
6. You should see a button, and when you press it the debugger will light up.

### Activate an RC automatically when the level is played
This can be accomplished using the [[RC Activator]] object, found under the Game category in the sandbox menu. Place an RC Activator in your level. While selected, choose the Crosshair button and select which RC the activator will activate.

By default the RC will be activated immediately, but you can activate it on demand by connecting a signal cable to the RC activator and sending a value of 1.0 when it should be activated.

### Let the camera follow an object
The [[Cam Targeter]] object can be used to set what object the camera will follow. First, find the Cam Targeter under the "Game" category in the sandbox menu. Place it in your level, click on the Crosshair-icon and the game will ask you to select an object. Click on an object you would like for the camera to follow.

The Cam Targeter will be automatically enabled when the game is started. You can activate it on demand by connecting a signal cable to it and sending a value of 1.0.
