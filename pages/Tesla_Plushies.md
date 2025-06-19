{{ infobox_game({
	"title": "Tesla Plushies",
	"image": "tesla_plushies.webp",
	"developer": "Bithack",
	"initial_release": "March 3, 2011",
	"last_release": "March 30, 2011",
	"platform": "Android"
}) }}

Tesla Plushies is a game developed by Bithack in 2011 and released for Android. It was the first mobile game published by Bithack, some months before the first version of Apparatus was released.

The game is claimed to have originally been paid, but was later made free. It was taken down from Google Play along with the rest of Bithack's games at an unknown point in time.

[toc]

## Gameplay
Tesla Plushies works by creating gravitational pulls on walls in order to affect how the round plushies move. The objective is to safely transport the plushies to the goal by doing this while avoiding obstacles. Some plushies have different colours that need to be transported to their respective goals, and there are angry plushies which give a score reduction if they end up in the goal.

## Download
The last version of Tesla Plushies, 1.0.3, can be [downloaded from here](https://archive.org/download/tesla-plushies-android-game-archive/TeslaPlushies_1.0.3.apk).

It requires Android 1.6+ and an ARM device that supports 32-bit binaries. The menu button is used in-game to exit from a level, which you will need a button remapper to access on Android 10+.

## Notes
Tesla Plushies was written in Java and developed with libGDX, the same framework later used by Apparatus. Tesla Plushies shares some code with Apparatus such as some UI primitives and to a certain extent the way the level format is structured.

Tesla Plushies was originally developed from an unreleased game by the name of Super Slime Blob. Some unused code for objects intended for this game remain in the game among other references to a `com.bithack.superslimeblob` package name.

The music soundtrack for the game is Democracy by Daniel Hjerth. The version found in the game is in mono with a low bitrate, but a higher quality stereo edition has surfaced which is available on [Youtube](https://www.youtube.com/watch?v=7vWOY3nhRlk) and [archive.org](https://archive.org/details/daniel-hjerth-democracy).

### Editor
A level editor was discovered ([video](https://www.youtube.com/watch?v=BRzALsEIMEs)) hidden in the code, which can be activated by changing the switch statement in `LoadingScreen::render()` to open the editor rather than the regular level select. A modded version of the game is available that exposes the editor, which [is available for download here](https://archive.org/download/teslap_editor_signed/teslap_editor_signed.apk).

The editor is very buggy and was likely intended to be used on desktop, not on mobile. Some notes for using the editor:

- It uses keyboard keys for various actions. Be sure to install something like hacker's keyboard where you can bring up a keyboard at all times.
- You move around with the WASD keys on the keyboard. There are some other keys that do stuff, but most either crash or do not work as intended.
- It saves level files to the "TeslaPlushiesLevels" folder in your storage. You may have to create this folder beforehand.
- The level editor saves (press U on the keyboard for saving) to a file called TESTLEVEL.jar. Be sure to rename it if you don't wanna overwrite it.

For playing the levels simply replace the custom jar file with a built in jar file.

### Desktop version
An unused class `TeslaPlushiesDesktop` exists within the game with an entrypoint to run the game with libGDX's JOGL backend on desktop, making the game able to run on a regular computer. Attempting to recompile the game from decompiled source code leads to other issues however, as the version of libGDX Tesla Plushies has either been modified or it is using a development version of libGDX from some point in time rather than a stable release.

### Source code
The source code of the game is currently believed to be lost. However as the compiled game has not been obfuscated and Java bytecode being generally easier to decompile than more traditional machine code, a serious decompilation effort to recreate a usable copy of the source code would be possible but has not been started yet.
