Throughout Principia's development, the level format has been changed to add new properties and features. In order to know which version a level file is saved in, the first byte of a level file is a numeric value denoting the version of the level format.

Principia is supposed to have backwards compatibility with old levels, containing compatibility code to load level versions as far back as Beta 5 (used for the Smiley Man level, oldest currently available level). However during certain updates there has been minor changes to existing gameplay functionality leading to issues trying to play older levels.

Level versions usually correspond to a version or date in development where changes have been made to warrant a new level version to make older versions compatible. Versions 1 through 14 are versions that were incremented prior to the 1.0 release and are usually referred to as "Beta 1" through "Beta 14", but are rare to see outside of very old levels created by Bithack developers and beta testers.

Below is a list of changes in behaviour and functionality between level versions:

[toc]

## 2023-06-05 (Version 30)
- Increased fluid particle limit (4096 -> 16384)
- Increased sticky note limit
- Remove LuaScript code encryption

## 1.5.1 (Version 29)
- New SFX emitter, different sound database and IDs
- Can now absorb creatures with the big absorber
- Adjusted section width of plants
- Adjusted layer mask of signal and interface clip
- New handling of textured pixels
- LuaScript baseline:
	- `game:prompt`
	- (Note: All new Lua functions added in FOSS Principia are available regardless of the level version as long as you are on version 29)

## 1.5 (Version 28)
- Compression of level data buffer
- Level loading is chunked, if level property is set
- Robots are now equipped with Builder, Zapper and Compressor by default
- Lots of new level properties
- 2D field and double-radial panel elements
- Pivot connection uses Joint friction level property instead of a per-connection damping property
- Encrypt LuaScript code with XOR cipher (LOL)
- Improvements to force of explosives
- Mini absorber can now absorb resources
- Mini emitter can now emit small plastic boxes and resources
- Absorber can now absorb resources and items
- Emitter can now emit items and resources
- Lots of LuaScript functions... (TODO)

## 1.4.0.2 (Version 27)
Nothing?

## 1.4 (Version 26)
- Emitter can now emit Lobbers, Bombers, Spikebots and Plastic boxes
- Absorber can now absorb Lobbers, Bombers, Spikebots and Plastic boxes
- Allow configuring friction and restitution for rubber beam and wheel
- Add Prismatic tolerance and Pivot tolerance properties to level header
- Something to do with level borders? (TODO)

## 1.3.0.3 (Version 25)
(TODO)

## 1.3.0.2 (Version 24)
(TODO)

## 1.3.0.1 (Version 23)
(TODO)

## 1.2.4 (Version 22)
(TODO)

## 1.2.3 (Version 21)
(TODO)

## 1.2.2 (Version 20)
(TODO)

## 1.2.1 (Version 19)
(TODO)

## 1.2 (Version 18)
(TODO)

## 1.1.7 (Version 17)
(TODO)

## 1.1.6 (Version 16)
(TODO)

## 1.0 (Version 15)
(TODO)

## Beta 14 (Version 14)
(TODO)

## Beta 13 (Version 13)
(TODO)

## Beta 12 (Version 12)
(TODO)

## Beta 11 (Version 11)
(TODO)

## Beta 10 (Version 10)
(TODO)

## Beta 9 (Version 9)
(TODO)

## Beta 8 (Version 8)
(TODO)

## Beta 7 (Version 7)
(TODO)

## Beta 6 (Version 6)
(TODO)

## Beta 5 (Version 5)
(TODO)

## Beta 4 (Version 4)
(TODO)

## Beta 3 (Version 3)
(TODO)

## Beta 2 (Version 2)
(TODO)

## Beta 1 (Version 1)
First 

## "Null" (Version 0)
This version number was never used. If it's shown the level file is most likely severely corrupted or not a level file at all.
