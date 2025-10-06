In this part of the adventure tutorial you will learn how to create an elevator, moving platforms, laser puzzle and more.

**[Example level with all contraptions included](https://principia-web.se/archive/level/6025)**

![](/wiki/images/imgur/wf8JAHv.webp)

[toc]

## Simple elevator 1
![](/wiki/images/imgur/KsuovNs.webp)

**Objects used:**
- **[[Linear Servo]]**
- **[[CT Servo]]**
- **[[Power Supply]]**
- **[[Sparsifier]]**
- **[[Condenser]]**
- **[[Inverter]]**
- **[[RC Basic]]**
- **[[Plastic Beam]]s**
- **[[Platform]]s**

Build a frame for the elevator using plastic beams. Attach it to one of the Linear Servos, then attach that Linear Servo to the other Linear Servo.

When the player uses one of the RC buttons a signal is sent through a Sparsifier, then to a Condenser, and finally to an Inverter.

The Condenser stores an internal value of the sum of all previous values read from **`IN0`**, minus all previous values read from **`IN1`**. The internal value is then divided by the maximum value and written to **`OUT0`** as a fraction.

![](/wiki/images/imgur/0bDvlo1.webp)

## Simple elevator 2
![](/wiki/images/imgur/1EDS7Zk.webp)

**Objects used:**
- **[[Thruster]]s**
- **[[Object field]]**
- **[[Stabilizer]]**
- **[[Mini transmitter]]**
- **[[Receiver]]s**
- **[[Wheel]]s**
- **[[Plastic Beam]]s**

This elevator uses thrusters instead of a motor. The thrusters are activated when a player enters the elevator and is seen by an object field on layer 2. If they switch layer the thrusters will stop and the elevator will go down. The stabilizer keeps the elevator from wobbling or falling too fast.

## Moving platforms
![](/wiki/images/imgur/dErVzQs.webp)

Objects used:
- **[[Linear Servo]]**
- **[[CT Servo]]**
- **[[Power Supply]]**
- **[[Sine wave]]**
- **[[Plastic Beam]]s**

Attach sine waves to each CT servos with different frequency, but make sure they sync properly so the player can jump between them.

## Ropeway
![](/wiki/images/imgur/k9IoU6A.webp)

Objects used:
- **[[Rope]]s**
- **[[Cylinder]]**
- **[[Plank]]s**
- **[[Platform]]s**

Attach a bunch of ropes together, build a small "basket" for the player to sit in and make it able to roll by using a cylinder above the ropes.

Optional objects (for unlock button):
- **[[Toggle Button]]**
- **[[Linear Motor]]**
- **[[CT Mini]]**
- **[[Power Supply]]**

![](/wiki/images/imgur/PnzCtut.webp)

## Fading pixels
Objects used:
- **[[Pixel]]s**
- **[[Broadcaster]]**
- **[[Sine wave]]**

Use the configuration button for the pixels and change the "opacity" number. That is the frequency the broadcasters will use. You can set the two broadcasters to broadcast to every other pixel and use a sine wave for each broadcaster with different frequency to make the pixels pulse at different speed (see example level).

![](/wiki/images/imgur/3ZoyOD9.webp)
