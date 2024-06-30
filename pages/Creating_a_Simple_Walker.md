There are many ways to create a walker. In this tutorial you will learn how to create one using sine waves and linear servo motors for moving the legs. If this is your first time using the sandbox, we recommend that you take a look at the Vehicle tutorials first.

## Creating the Walker
First, create a new custom level.

We will begin by creating two legs made of a [[Plank]] and [[Damper]] attached to feet made of [[Rubber Beam]]s. One leg should be on layer 1 and the other on layer 2. Click the configuration button for the Rubber Beam and set the restitution to 0 and friction to 10, this will make the foot grip better when walking.

![](/wiki/images/imgur/ZfubrZ0.webp)

Move the legs beside each other and add two [[Linear Servo]]s. Make them horizontal and attach them to each leg as shown on the screenshot. Add two more Linear Servos, make them vertical and a bit larger, then attach them above the other two motors. These four motors will be used to move the legs. Change to Orthographic View to easier place them in the right position.

![](/wiki/images/imgur/pv1Y3Ua.webp)

Create a simple upper body frame using planks that connects the motors on the different layers and where we can place all the objects that will be used.

![](/wiki/images/imgur/Gn8WUl5.webp)

Add a [[Power Supply]] in the middle and four [[CT Servo]]s, one for each motor.

![](/wiki/images/imgur/sxkgz1d.webp)

Connect the CT Servos to the Linear Servos and to the Power Supply. When working with different layers, change the layer visibility for a better view. You might also have to increase the length of some of the [[Interface Cable]]s. Just detach them to adjust the slider.

![](/wiki/images/imgur/OGMHGoT.webp)

Add a [[Tiltmeter]] in the middle above the Power Supply and connect it to two [[Thruster]]s on the sides. The Tiltmeter will output the angular displacement of the tiltmeter relative to its standing position and then activate the Thruster that's on the side where the walker tilts towards. This is to make sure the walker doesn't tip over. Leave the thrust as default now, we will fine tune everything later.

![](/wiki/images/imgur/smUdR1Z.webp)

To make the legs go up and down we will now add two [[Sine wave]] objects. This is an electronic device that outputs a smooth repetitive oscillation. The phase determines where in the sine wave it begins. Set the frequency Hz to 0.60 on both sine wave objects and set the phase to 0.25 on one of them for now, we can change these later when fine tuning.

Add two [[muladd]] objects and connect them to the sine wave objects. Set the multiply slider to 2. This will multiply the sine wave so that when it reaches the end of the Linear Servo it makes a small pause. This will make the walking more stable by stopping the foot when it hits the ground while the other foot is in the air.

You can use a [[Grapher]] to see a demonstration of what happens to the sine wave when multiplying it.

![](/wiki/images/imgur/GMPATgu.webp)

![](/wiki/images/imgur/xNmHhn9.webp)

Now we have an up and down motion for the legs. To be able to walk properly we need to add a side to side motion to the two vertical Linear Servos above the legs. Add two more Sine wave objects and two [[Inverter]]s. Set the frequency Hz of the Sine waves to 0.60 and set the phase to 0.25 and 0.50 for now, then connect them to the Inverters. That will invert the sine wave and make the walker move to the right.

![](/wiki/images/imgur/9mIvPv4.webp)

## Fine Tuning
The leg motion is now finished but before the walker can walk properly we need to do some fine tuning.

The values that will be used now depends on the size and weight of your walker. If you have made your walker slightly different than the one in this tutorial you can begin with these values, then test it and make any changes if necessary.

First, click the two vertical Linear Servos and change the "Speed - Force" slider to 0.40. If you use more force than that the speed will be set to 0 and the walker won't move.

![](/wiki/images/imgur/GSgAutC.webp)

- Click the two horizontal Linear Servos and increase the Force slightly (0.10).
- Click the Power Supply and decrease the voltage to 5.00.
- Click the Tiltmeter and increase the sensitivity to 17.00. Set the thrust of the Thrusters to 14.00.

The walker should now walk properly and not tip over but to make it even more stable we can use a [[Stabilizer]] object. Add it somewhere in the middle and increase the angular damping just a bit (~0.20).

![](/wiki/images/imgur/3rnRIBs.webp)

If the walking still is unstable you can try changing the frequency Hz and/or phase slider of the [[Sine wave]] objects. See if something is out of sync. The legs should have a half-circle motion and not move too fast.

Feel free to make any additional upgrades to your walker. For example an upper body, a cannon or add two more legs to make it a four legged walker! If you're happy with it you can publish it and share it with the community!

## [Example Level](https://archive.principia-web.se/level/6585)
