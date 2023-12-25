{{ infobox_object({
	"id": 156,
	"name": "Event Listener",
	"category": "Signal-misc",
	"sublayer_width": 14
}) }}

Listens to the event specified with the config menu and outputs a 1 to **`OUT0`** whenever the event occurred.

Events can also be listened to from Lua using the [`on_event`](/wiki/LuaScript/Callbacks#on-event) callback function. The ID will be the first argument, and constants are available to easier check for particular event types.

## Available events

| ID  | Lua constant                | Name                         | Description                                                |
| --- | --------------------------- | ---------------------------- | ---------------------------------------------------------- |
| `0` | `EVENT_PLAYER_DIE`          | Player die                   | The adventure robot is killed.                             |
| `1` | `EVENT_ENEMY_DIE`           | Enemy die                    | Any robot other than the adventure robot is killed.        |
| `2` | `EVENT_INTERACTIVE_DESTROY` | Interactive object destroyed | Any interactive object is destroyed.                       |
| `3` | `EVENT_PLAYER_RESPAWN`      | Player respawn               | The adventure robot respawns.                              |
| `4` | `EVENT_CLICK_DOWN`          | Touch/Mouse click            | The player clicks somewhere on the screen.                 |
| `5` | `EVENT_CLICK_UP`            | Touch/Mouse release          | The player releases that click.                            |
| `6` | `EVENT_ABSORB`              | Any absorber activated       | As specified, when any absorber on the level is activated. |
