Hacked Signals refer to any signal value outside the regular 0.0 to 1.0 range. They are unsupported and make objects behave in unexpected and erratic ways.

Hacked signals outside of the regular range are normally unobtainable in normal sandbox gameplay. However they can be obtained by, for example, hex editing the value of a [[Jumper]] to send a signal outside of the 0.0-1.0 range.

Some objects will clamp the input signal to the 0.0-1.0 range, while others will use the signal value as-is. The behaviour of objects when they receive a hacked signal, and if they will clamp the value, is undefined and can change at any point in the future.

*This page is a stub, feel free to expand it.*
