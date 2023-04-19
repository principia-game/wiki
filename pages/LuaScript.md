{{ infobox_object({
	"id": 184,
	"name": "LuaScript",
	"category": "Tools/effects",
	"sublayer_width": 14,
}) }}

Lua Script object, write Lua programs that can interact with and control the level.

For more information about Lua scripting in Principia, see [[Principia Lua Scripting]]

# Libraries
The following built-in libraries are available in the Principia Lua environment:
- `math`
- `string` (older versions require a flag to be enabled)
- `table` (older versions require a flag to be enabled)
- `bitop32` ^(1.5.2+)^

# Classes
The API is divided up into several classes:

* **[`this`](/wiki/LuaScript/this)**: A reference to the unique LuaScript object itself, with methods that relate to the current LuaScript object.
* **[`game`](/wiki/LuaScript/game)**: A global object containing *game* related methods.
* **[`cam`](/wiki/LuaScript/cam)**: A global object containing *camera* related methods.
* **[`world`](/wiki/LuaScript/world)**: A global object containing *world* related methods.
* **[`entity`](/wiki/LuaScript/entity)**: Reference to a Principia game object, which can be retrieved using `world:get_entity()`.
  * **[`creature`](/wiki/LuaScript/creature)**: Extension of the `entity` class for living objects such as robots.