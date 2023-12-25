{{ infobox_object({
	"id": 184,
	"name": "LuaScript",
	"category": "Tools/effects",
	"sublayer_width": 14
}) }}

Lua Script object, write Lua programs that can interact with and control the level.

For more information about Lua scripting in Principia, see [[Principia Lua Scripting]].

## Libraries
The following built-in libraries are available in the Principia Lua environment:
- **[`math`](https://www.lua.org/manual/5.2/manual.html#6.6)**
- **[`string`](https://www.lua.org/manual/5.2/manual.html#6.4)** (older versions require a flag to be enabled)
- **[`table`](https://www.lua.org/manual/5.2/manual.html#6.5)** (older versions require a flag to be enabled)
- **[`bitop32`](https://www.lua.org/manual/5.2/manual.html#6.7)** ^(1.5.2+)^

## API reference

* **[`this`](/wiki/LuaScript/this)**: Reference to the unique LuaScript object itself, with methods that relate to the current LuaScript object.
* **[`game`](/wiki/LuaScript/game)**: Global object containing *game* related methods.
* **[`cam`](/wiki/LuaScript/cam)**: Global object containing *camera* related methods.
* **[`world`](/wiki/LuaScript/world)**: Global object containing *world* related methods.
* **[`entity`](/wiki/LuaScript/entity)**: Reference to a Principia game object, which can be retrieved using `world:get_entity()`.
  * **[`creature`](/wiki/LuaScript/creature)**: Extension of the `entity` class for living objects such as robots.
* **[Callbacks](/wiki/LuaScript/Callbacks)**: List of callbacks.
