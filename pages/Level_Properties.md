[toc]

## Info
- **Name**

	The title or name of your level, which will be visible on the community site should you choose to publish it.

- **Description**

	A description of your level, mandatory if you want to publish it.

- **Type**

	Specify the type of the level, Adventure or Custom.

## World
- **Background**

	Select one of the available backgrounds to use for your level.

	- **Background colour**

	Colour of background if a coloured background has been used.

- **Left/Right/Bottom/Top border**

	Expand the level size by increasing these values.

- **Gravity X/Y**

	Modify the gravity of your level. Default X=0 Y=-20

## Physics

- **Position iterations/Velocity iterations**

	The Position and Velocity iterations can be increased to improve precision of the simulation, at the cost of performance. It is recommended that you set the number of iterations as low as possible, as it will allow players with less powerful devices to play your level.

- **Prismatic tolerance**

	TODO

- **Pivot tolerance**

	TODO

- **Linear damping**

	TODO

- **Angular damping**

	TODO

- **Joint friction**

	TODO

## Gameplay
- **Final Score**

	What score the player has to reach to win a level.

- **Level Version**

	The version the level uses which may affect the features that are available or how physics behaves.

- **Pause on win**

	Pause the simulation once the win condition has been reached.

- **Display score**

	Display the score in the top-right corner.

- **Creature absorb time**

	Time before dead creatures are absorbed.

- **Player respawn time**

	The duration of the respawn cooldown when the player dies.

- **Disable layer switch**

	Adventure mode: Disable manual layer-switching of robots. Puzzle mode: Disable layer switching of objects.

- **Disable interactive**

	Disable the ability to handle interactive objects.

- **Disable fall damage**

	Disable the damage robots take when they fall.

- **Disable connections**

	Puzzle mode only, disable the ability to create connections.

- **Disable static connections**

	Puzzle mode only, disable connections to static objects such as platforms.

- **Disable jumping**

	Adventure mode only, disable the robots ability to manually jump.

- **Disable robot hit score**

	(adventure mode only?) Disable score increase by shooting other robots.

- **Disable zoom**

	Disable the players ability to zoom.

- **Disable cam movement**

	Disable the players ability to move the camera.

- **Disable initial wait**

	Disable the waiting state when a level is started.

- **Unlimited enemy vision**

	Adventure mode only, if enabled, enemy robots will see the player from any distance and through any obstacles, and always try to find a path to the player.

- **Interactive destruction**

	If enabled, interactive objects can be destroying by shooting them a few times or blowing them up.

- **Absorb dead enemies**

	If enabled, dead enemies will disappear from the game after a short interval after they die.

- **Snap by default**

	For puzzle levels, when the player drags or rotates an object it will snap to a grid by default (good for easy beginner levels).

- **Hide beam connections**

	Use less visible nail-shaped connections for planks and beams. Existing connections will not be changed if this flag is changed.

- **Disable continue button**

	If initial wait is disabled, this option disabled the continue button inf the lower right corner. Use pkg warp to go to the next level instead.

- **Single-layer explosions**

	Enable this flag to prevent explosions from reaching objects in other layers.

- **Disable damage**

	Disable damage to any robot.

- **Disable third layer**

	Puzzle mode only, disable moving objects to the third layer, effectively limiting the player to two layers.

- **Portrait Mode**

	If enabled, the view will be set to portrait mode (vertical) during play.

- **Disable RC camera snap**

	If enabled, the camera won't snap to any activated RC.

- **Disable physics**

	If enabled, physics simulation in the level will be disabled.

- **Do not require dragfield**

	If enabled, the player can move all interactive objects in the game without a dragfield

- **Disable robot special action**

	If enabled, the adventure robot cannot perform its special action.

- **Disable adventure max zoom**

	If enabled, the zoom is no longer limited when following the adventure robot.

- **Disable roam layer switch**

	Disable the roaming robots ability to change layer.

- **Chunked level loading**

	Splits up the level into chunks, leading to better performance for large levels.

- **Disable adventure caveview**

	Disable the caveview which appears when the adventure robot is in layer two, with terrain in front of him in layer three.

- **Disable rocket triggering explosives**

	Disable the rocket from triggering any explosives when contact with its flames occurs.

- **Store high score on game over**

	Allow players to submit a high score even if they did not win the level.

- **Allow high score submissions**

	Allow players to submit their high scores to be displayed on your levels community page.

- **Lower score is better**

	A lower score is considered better than a higher score.

- **Automatically submit score on finish**

	Automatically submit score for the user when the level finishes.

- **Disable end-screens**

	Disable any end-game sound or messages. Works well when Pause on WIN is disabled. Note that this also disabled the score submission button. To submit highscore without the button you can use the [[LuaScript]] function game:submit_score().

- **Allow quicksaving**

	If enabled, the player can save his progress at any time.

- **Allow respawn without checkpoint**

	If disabled, robots cannot respawn if they are not connected to any checkpoint.

- **Allow dead creature destruction**

	If enabled, creature corpses can be destroyed by shooting them.
