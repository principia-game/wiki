Principia is the spiritual successor to Apparatus. There are a lot of similarities between them, but Principia is also significantly more advanced than Apparatus and behaves differently in some ways. This page contains information that would be useful for Apparatus players wanting to try out Principia.

[toc]

## Principia equivalents to Apparatus objects
Principia has a significantly larger selection of objects available at your disposal, including advanced signal circuiting and even Lua scripting. However, the objects that existed in Apparatus still exist in Principia in some form.

### Wooden
- [[Cylinder]]
- [[Plank]]
- [[Rubberband]]

### "Harder" objects
- [[Weight]]
- [[Platform]]
- [[Wheel]]

### Electronics
- Control panel: can be recreated with [[RC Basic]], see [Notes/Pitfalls: RC Widgets](#rc-widgets)
- [[Signal Cable]]
- [[Power Cable]]
- [[Power Supply]]
- Loose Motor: equivalent to [[Simple Motor]]
- Static Motor: can be recreated by attaching a [[Simple Motor]] to a [[Platform]] or anything else stationary.

### Interactive/Game
- Interactive red cylinder: can be recreated with interactive Principia objects, but keep in mind they have different behaviour.
- Marble goal: Can be recreated with the [[Plastic Cup]] or [[Plastic Beam]]s, with an [[Object finder]] connected to a [[Game Manager]]'s **`IN0`** socket to make it win the level when a ball rolls into it.
- Marble: Any kind of ball object, see Marble goal.

### Misc.
- [[Damper]]
- [[Button]] (one-time use button)
- [[Rocket]]
- Cable Hub:
  - For boosting motor voltage by combining power supplies, you can boost the [[Power Supply]] voltage much higher in Principia than in Apparatus.
  - For making one panel button control several motors use the [[Y-splitter]].
- Explosive: [[Land mine]]

## Notes/Pitfalls

### Level size
The level size is very configurable in Principia, as compared to Apparatus where the level is limited to a certain size. Objects can fall out of bounds in Apparatus, while with most backgrounds in Principia there are wooden walls to keep everything inside. To simulate an Apparatus-like level size you could increase the size to e.g. 300 in each direction to get.

### Building in the sandbox
Principia comes with a great deal of quality-of-life improvements when it comes to building levels. This includes a dedicated "construction"/"orthographic" mode which can be toggled to get a fine-grained grid control over the placement and rotation of your objects. If you are on a touchscreen then the two-finger salute to align against a hidden grid from Apparatus still exists however (Desktop players can hold down the Shift key to get a similar behaviour).

If you are on a computer then you should read through the Sandbox section of the [[PC Controls]] page, as there are very powerful keybinds to quickly do particular things in Principia like duplicating objects with the comma (,) key.

### Destruction
Joints and connections are indestructible by default in Principia, as compared to Apparatus where connections always have a risk of breaking. Under the advanced sandbox menu options there's the Connection Edit mode which allows you to change the strength of individual connections, or you can use the Multi-Select configuration menu which can change the connection strength in bulk on a selected group.

Cables cannot be ripped out of their sockets in Principia, and there is no way to change the behaviour to that of Apparatus. To make something more destructible you may choose to replace [[Signal Cable]]s with wireless [[Receiver]]s and [[Mini transmitter]]s.

### RC Widgets
In Principia, you can customise RC widgets as compared to in Apparatus where they are hardcoded depending on the amount of panel sockets. You can choose to recreate the setup of the Apparatus panels, but you might want to create a more unique control scheme anyways.

### Interactive objects
Interactive objects in Principia behave differently to how they do in Apparatus. The red cylinder in Apparatus is able to apply seemingly infinite force to follow the finger, while interactive objects in Principia may be dropped if it can't follow the cursor. By default interactive objects need be within range of a [[Dragfield]] or the unlimited interactive level property enabled.
