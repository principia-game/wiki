A reference to a Principia creature.

**NOTE:** Most entity-functions also work on creature, see creature as an extension to [`entity`](/wiki/LuaScript/entity).

[toc]

## `creature:get_hp()`
Added in **1.5**

Returns the HP and max HP of the creature.

```lua
local hp, max_hp = creature:get_hp()
```

## `creature:get_armor()`
Added in **1.5**

Returns the armor and max armor of the creature.

```lua
local armor, max_armor = creature:get_armor()
```

## `creature:get_aim()`
Added in **1.5**

Returns the aim of the current creature, assuming it can aim.

```lua
local aim = creature:get_aim()
```

## `creature:set_aim()`
Added in **1.5**

Sets the weapon arm angle for the creature, if applicable.

```lua
creature:set_aim(new_aim)
```

## `creature:stop()`
Added in **1.5**

Stop the creature from walking in the given direction. If no direction is given, the creature stops moving in all directions. (left = -1, right = 1, down = 0, up = 2)

```lua
creature:stop(direction = all)
```

## `creature:move()`
Added in **1.5**

Tell the creature to start moving in the given direction. (left = -1, right = 1, down = 0, up = 2)

```lua
creature:move(direction)
```

## `creature:is_action_active()`
Added in **1.5**

Returns true if the creature has their special action activated.

```lua
if creature:is_action_active() then
    game:message(creature:get_name() .. ' has their action activated!!')
end
```

## `creature:action_on()`
Added in **1.5**

Toggles the creature's special action on.

```lua
creature:action_on()
```

## `creature:action_off()`
Added in **1.5**

Toggles the creature's special action off.

```lua
creature:action_off()
```
