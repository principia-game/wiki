This page is a historical reference over official release notes for Principia versions prior to the open source release collected from various places.

To download old versions of Principia prior to the open source release please see the [Bithack Game Archive](https://docs.google.com/spreadsheets/d/1G2YX0BV9_FSrIOvbCQtgYLE1XirCr8UaAfXUzuxjefE/htmlview).

[toc]

## Principia 1.5
1.5 "Exploration Update"

### Changes in 1.5.1
- Graphics improvements
- Added King's Crown
- Added Dummy Head
- Added Stone head decoration
- Added Jester Hat
- Added Wood sword
- Added Hammer
- Added Simple Axe
- Added Witch hat
- Added Chainsaw
- Added Spiked Club
- Added Steel Sword
- Added Baseball bat
- Added Spear
- Added War axe
- Added Pixel sword
- Added Hard hat
- Added Serpent sword
- Added Pioneer robot front and back
- Added Viking Helmet
- Added Pickaxe
- New enemy: Mini Spikebot
- Updated conical hat texture
- Bugfix: proximity sensor sometimes did not detect anything
- Added ground plant decorations
- Improved SFX Emitter.
  NOTE: Upgrading old levels with SFX Emitters will make it play other sounds.

### Changes in 1.5.0.5
- Fixed a crash related to emitting of robots with jetpacks equipped. (thanks Golden)
- LuaScript tracker function now shows the objects change as well.
- Polygon now have their own 4 connections at the midpoint inbetween corners.
- PC: Activating RCs/Backpacks/any activator in adventure mode should be a bit more intuitive now, showing different bindings for different objects.
- Android: State-loading a sandbox level no longer removes the option to return to sandbox.

### Changes in 1.5.0.4
- Camera rotator renamed to Cam Rotator
- Fixed a crash bug with Android puzzles

### Changes in 1.5.0.3
- Fixed an issue related to dragging platforms out from the menu.
- Softer sounds added to the menu buttons. (from Kenney.nl)
- Fixed a crash in adventure mode that occured when many objects were absorbed at once.
- Some decorations can now be rotated using the rotation slider.
- Vendor dialog fixed for Android
- Robots now update their equipment immediately after exiting the dialog.
- LuaScript tracker icon now works as expected on Android.
- It's now possible to delete saves on Android.

### Changes in 1.5.0.2
- Multiselect config dialog fixed for Android
- Rockets no longer trigger explosives in other layers (1.5 and up only)
- Tuned quadruped leg damage
- Bugfix: It's now possible to disconnect from RCs in adventure mode
- Ladder steps can now be zapped
- Multi-importing old objects should now work flawlessly.
- Portrait mode fixed

### Changes in 1.5
- Support for generating adventure worlds that can be explored
- Big improvements to robot AI
- Robots are now modular and can replace and remove parts
- Added robot factions (friendly, enemy, etc.)
- Support for installing feature circuits into robots
- New underground vision
- Various graphics improvements
- Support for saving levels while playing
- Support for custom colored backgrounds
- Lua objects are now invoked by function (see forum thread)
- Rockets now trigger all explosives. This can be disabled in a level property.
- Added a damage slider to the explosives.
- Stabilizer now has two inputs
- Timer can now optionally use system time instead of game time
- Consumable renamed to Item
- Various new PC keyboard shortcuts
- New RC widgets: Radial with centre button, 2x2 field and 3x3 field
- Various bugfixes
- Fixed an issue where community levels sometimes had to be restarted once to work correctly
- More realistic default physics settings
- Loading screens are now more verbose
- Fixed a bug that could cause large objects to rotate randomly in the sandbox after a connection is destroyed
- Multiselect mode now allows you to customize its behaviour
- Multiselect mode now lets you perform actions across all selected objects using the config button
- New objects:
  - Robot Factory, constructs robots
  - Armory, constructs weapons and armor
  - Oil Mixer, mixes power up oils
  - Guard Point, robots will guard a location
  - Suction Cup
  - Cleaner bot, a robot that gathers scrap
  - Repair Station, install and manage robot hardware
  - Target Setter, specify a target for a robot
  - Ladder, can be climbed by the adventure bot
  - Robot Manager, a monster device for managing a robot remotely
  - Animal, robot cow or pig
  - Plant, trees and various vegetation
  - Vendor
  - Sound Manager, catch and replace in-game sounds
  - State Saver, invokes a level save
  - Player Activator, dynamically switches which robot is being controlled
  - Key Listener, reports when a keyboard key is pressed
  - Polygon, customizable shape
  - Level Manager, set level light intensity
  - Resource
  - IF-select
- New Items:
  - Rocket Launcher
  - Bomb Launcher
  - Tesla Gun
  - Plasma Gun
  - Mega Buster
  - Heisenberg's Hat
  - Ninja Helmet
  - Black Robe
  - Somersault Circuit
  - Jetpack
  - Upgraded Jetpack
  - Advanced Jetpack
  - Loose head, body, cow head, pig head
- New Lua functions:
  - entity:damage() - damage an entity if it supports taking damage
  - entity:is_static() - true/false whether the entity is static
  - entity:absorb()
  - entity:apply_torque()
  - entity:set_velocity()
  - entity:warp()
  - entity:show()
  - entity:hide()
  - entity:get_name()
  - entity:is_creature()
  - entity:is_robot()
  - entity:is_player()
  - entity:get/set_color()
  - entity:disconnect_all()
  - creature:get_hp()
  - creature:get_armor()
  - creature:get_aim()
  - creature:set_aim()
  - creature:stop()
  - creature:move()
  - creature:is_action_active()
  - creature:action_on()
  - creature:action_off()
  - game:get_screen_cursor()
  - game:restart()
  - game:submit_score()
  - game:get/set_variable()
  - game:get_fps()
  - this:has_plug()
  - this:set_draw_coordinates() - world, screen or local coordinate system
  - this:get_resolution() - get the screen resolution
  - this:get_ratio() - get the screen ratio
  - this:add_static_sprite()
  - this:clear_static_sprite()
  - this:draw_line_3d()
  - this:draw_gradient_line_3d()
  - this:draw_gradient_line()
  - this:get_id()
  - this:get_sprite_texel()
  - world:get_entity() - alias for world:get_entity_by_id()
  - world:get_adventure_id()
  - world:get_borders()
  - world:get_world_point()
  - world:get_screen_point()
  - world:set_bg_color()
- New level properties:
  - Flag: Enable chunked level loading
  - Flag: Disable caveview
  - Flag: Disable rocket explosive triggering
  - Flag: Store score on game over
  - Flag: Allow high score submissions
  - Flag: Lower score is better
  - Flag: Disable end-screens
  - Flag: Allow quicksaving
  - Linear damping
  - Angular damping
  - Joint friction


## Principia 1.4
Principia 1.4 "Adventure Update" was released on February 10th, 2014.

### Changes in 1.4.0.1 to 1.4.0.4
- First PC and iOS releases
- Various bug fixes
- Factory sliding fixed
- Fixed ugly factory rendering
- Conveyor did not work on bedrock

### Changes in 1.4 - February 10th, 2014
- Robot movement revised
- Added support for in-game adventure building
- Robot can now equip different weapons and tools on each arm
- 2 new main levels (1 medium, 1 hard)
- Textured pixels
- Terrain painting in sandbox
- Support for mining terrain
- New object: Oil Rig
- New object: Crane
- New object: Factory, for constructing objects in adventure mode
- New object: Artifical Gravity
- New object: Shape Extruder
- New object: Plastic Box
- New object: Fluid
- New object: Boundary (i1o1)
- Added gem stones
- Added various power-up oils and basic oil mixing
- Robot armour system
- New weapon: Shotgun
- New weapon: Railgun
- New tool: Builder tool
- New tool: Mining tool
- Added a smaller platform size
- Voltage system revised (does not affect old levels)
- Various issues with multi-part objects (damper, open pivot) fixed
- Servo Motor now has a speed cap option
- Bugfix: Fan applied forces across layers
- Bugfix: servo motor had mismatching CCW/CW speeds
- Bugfix: Robot could layermove through objects once
- Bugfix: Robot jump was weird sometimes
- Bugfix: Object/ID field improperly reported dummys and a few other object types
- New widgets: 3x1 slider, vertical sliders, 3x3 radial
- Conveyor can now be made dynamic
- Mini emitters and absorbers can now handle the smallest cylinder
- Emitters/absorbers can now handle all types of robots
- Digital Display renamed to Passive Display
- Added Active Display
- Robot can now box himself for protection
- Improved exlosion and rocket effects
- New physics stability options: prismatic and pivot error tolerance
- New Lua methods: world:raycast, world:query, entity:highlight, entity:get_layer, this:draw_line, this:listen_on_frequency, this:read_frequency, this:clear_texels, game:message, game:poll_event, game:get_cursor(), world:get_gravity(), entity:local_to_world(), entity:world_to_local()
- Lua set_sprite_tint and set_sprite_z renamed to set_draw_tint and set_draw_z
- Rubber objects can now specify custom restitution/friction values.


## Principia 1.3
Principia 1.3 "Christmas Update" was released on December 20th. It added support for Lua scripting, performance improments and much more.

### Changes in 1.3
- Huge performance improvements, up to 300% boost on big levels
- Performance improvements to all effects
- Triangle waveform added to synthesizer
- Almost all objects now have proper descriptions
- The camera now moves automatically when you drag an object against a screen border
- New level property: Do not require dragfields
- Power Supply max voltage doubled to 48V
- New object: Cursor Field, an invisible, resizable touch-detector. Alfajim, this is what you should use for your synth and piano. ;)
- Added object quickadd dialog (search by name)
- New sandbox menu category sorting
- Improvements to sandbox menu
- New object: Lua Script
- Jumper now has a precision-value dialog
- Damage slider added to Spikes
- Increased max zoom-out of Cam Marker
- Bugfix: Linear decay slider error
- Bugfix: Checkpoint only worked in layer 1
- Bugfix: disconnected sockets "remembered" their last value
- Improvements to adventure robot


## Principia 1.2

### Changes in 1.2.4
- Added a config dialog for the Jumper for high-precision needs.
- Experimental triangle wave added to the Synthesizer.
- Huge performance boost (up to 300%) to levels that are use static objects
- Added a slider to the spikes for Damage.
- Increased the maximum zoom for the Cam Marker
- A lot of object descriptions added or refined.
- Bugfixes:
  - Linear decay slider
  - Checkpoint only worked in layer 1
  - Sockets didn't properly reset their value on pause
- Dragging an object in to the border of the screen now moves the camera with the object. This can be disabled in the settings dialog.
- The adventure robot should be less 'jumpy' when colliding with his body against objects.
- FX Emitter performance boost. (???)
- New level property: 'Do not require dragfield'
- Power supply max voltage doubled, have fun!
- New object: Cursor field. Use this object to track the players cursor/finger movement inside the specified field.

### Changes in 1.2.3
- Fixed a graphics issue on Galaxy Tab 3
- New objects: Linear Decay, Limit
- Rope much more stable

### Changes in 1.2.2
- New object: Sequencer
- Fixed a crash that occured when no internet connection was available
- Revised electronics solver (150% performance boost)
- New camera settings
- Portrait mode bugfixes
- Many other bugfixes

### Changes in 1.2.1
- Added a bunch of drum sounds to the SFX Emitter
- Added a lot more options to the Synthesizer
- New level property: Disable physics
- Bugfix: Snap can no longer output values above 1.0
- Various other bugfixes
- It's now possible to change the level type in the Level Properties dialog

### Changes in 1.2
- 10 New objects
  - Var getter & setter, for storing level persistant values
  - SFX Emitter, Wrap Condenser, IF-else, cmp-e, cmp-l, cmp-le, snap
  - Synthesizer for generating sound (BETA)
- New sandbox menu
- New level property: Portrait mode, great for minigames like pinball
- New level property: Disable auto RC cam follow
- Many bugfixes


## Principia 1.1
Versions before 1.1.2 did not keep a proper record of the changes.

### Changes in 1.1.7.1
- Now allowing external storage installations
- It's now possible to delete levels by long-pressing them in the Open dialog
- Various bugfixes

### Changes in 1.1.7
- New object: Signal Graph
- Sensitivity slider for tiltmeter
- Bugfixes related to Time Ctrl object

### Changes in 1.1.6
- Touch input fine-tuning
- New object: Cam Zoomer
- New object: Time control
- New object: Prompt
- Bugfix: Glitch when jumping in adventure mode
- Bugfix: Too many sticky notes crashed the game
- Bugfix: Switch object did not reset properly after play/pause
- Various tiny object bugfixes
- Various object size/model fixes
- Help labels are now rendered above sockets
- RC override values now working properly
- Increased friction of wheel (does not affect old levels)

### Changes in 1.1.5.1
- Bugfix: The loader is now a lot more failsafe. In case of a crash, the settings file is reduced to lower graphics in an attempt to let the game load properly.

### Changes in 1.1.5
- Bugfix: Game progress was lost if phone went to sleep during loading screen
- Transmitted 0-values now have low priority
- Initial value of toggler can now be set
- Added a settings button in the main menu
- Implemented object snap movement/rotation. While moving or rotating an object, hold down another finger to enable snap
- Level 21 can now be completed

### Changes in 1.1.4
- Bombs can now be destroyed using lasers.
- Rope rendering bugfixes.
- Command pad could not aim left.
- Sparsifier bugfix.
- Main level bugfixes.
- Rocket/Thruster sublayer fixes.

### Changes in 1.1.3
- 2 new levels
- Fixed some text size issues on high-density devices
- Electronic device labels now fade out when zoomed out
- Smaller game size
- Various bugfixes

### Changes in 1.1.2
- Implemented Autosave in the sandbox
- Fixed some texture issues
- Improved handling of back button and pausing/resuming
- Adventure mode bugfixes
