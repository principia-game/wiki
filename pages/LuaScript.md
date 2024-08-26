{{ infobox_object({
	"id": 184,
	"name": "LuaScript",
	"category": "Tools/effects",
	"sublayer_width": 14
}) }}

Scriptable object, write your own Lua programs that can interact with and control the level. This allows for more complex creations and games, being able to draw arbitrary graphics and more.

Lua is a small programming language that focuses on being easily embeddable within other programs. You may have stumbled upon it being used somewhere else. Every program implements its own API on top of the Lua standard library, including Principia. Don't expect any non-standard Lua standard library extensions provided in other programs to necessarily exist in Principia.

Principia uses Lua version 5.2, so any generic tutorials for Lua 5.2 should apply to Principia as well. For general information about the programming language see the [Lua 5.2 Reference Manual](https://www.lua.org/manual/5.2/).

For help with Lua you can ask either in the `#lua` channel in the Principia Discord or in the [Lua](/forum/forum?id=4) forum.

## Libraries
The following built-in libraries are available in the Principia Lua environment:

- **[`math`](https://www.lua.org/manual/5.2/manual.html#6.6)**
- **[`string`](https://www.lua.org/manual/5.2/manual.html#6.4)** (older versions require a flag to be enabled)
- **[`table`](https://www.lua.org/manual/5.2/manual.html#6.5)** (older versions require a flag to be enabled)
- **[`bitop32`](https://www.lua.org/manual/5.2/manual.html#6.7)** ^(1.5.2+)^

## API reference
In addition to the reference, you can see [[LuaScript/Examples]] for small complete examples that use the API.

- **[`this`](/wiki/LuaScript/this)**: Reference to the unique LuaScript object itself, with methods that relate to the current LuaScript object.
- **[`game`](/wiki/LuaScript/game)**: Global object containing *game* related methods.
- **[`cam`](/wiki/LuaScript/cam)**: Global object containing *camera* related methods.
- **[`world`](/wiki/LuaScript/world)**: Global object containing *world* related methods.
- **[`entity`](/wiki/LuaScript/entity)**: Reference to a Principia game object, which can be retrieved using `world:get_entity()`.
  - **[`creature`](/wiki/LuaScript/creature)**: Extension of the `entity` class for living objects such as robots.
- **[Callbacks](/wiki/LuaScript/Callbacks)**: List of callbacks.

## Other resources
- [[LuaScript/Examples]] - Small examples of using the LuaScript API
- [[Learning Lua Scripting with Principia]] by zardOz
- [Principia Lua image converter](/image-to-lua/)
- [Principia LuaScript API cheatsheet](https://rollerozxa.itch.io/principia-luascript-api-cheatsheet) - Printable overview of the API
