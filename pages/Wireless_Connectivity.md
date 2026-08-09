The wireless connectivity system in Principia allows for signals to be transmitted wirelessly rather than using physical [[Signal Cable]]s. This allows for more compact builds where clutter can be hidden away from view by the player.

Each level has a frequency range between 0 and 4,294,967,295 and an infinite amount of receivers can listen to a single frequency regardless of the range. Multiple transmitters can be used on the same frequency, and the one sending a non-zero value will take precedent over the others. If multiple transmitters are transmitting non-zero values at the same time, the value actually transmitted is undefined.

## Objects
The following objects work with the wireless connectivity system:

- **Transmitters:**
	- [[Transmitter]]
	- [[Broadcaster]]
	- [[Mini transmitter]]
- **Receivers:**
	- [[Receiver]]
	- [[Pixel]]

## Lua
The [[LuaScript]] object can be used to transmit and listen to wireless signals with the following methods:

- [`this:write_frequency(frequency, value)`](/wiki/LuaScript/this#this-write-frequency)
- [`this:listen_on_frequency(frequency)`](/wiki/LuaScript/this#this-listen-on-frequency)
- [`this:read_frequency(frequency)`](/wiki/LuaScript/this#this-read-frequency)
