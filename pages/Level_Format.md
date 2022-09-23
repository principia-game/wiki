Principia stores levels with their filename as an incrementing integer counter and with the file extension `.plvl`. For sandbox levels they get saved into `lvl/local/` in the Principia user data path, played community levels get downloaded into `lvl/db/` for what seems to be caching purposes.

## Level versions
Throughout Principia's development, the level format has been changed to add new properties and features. In order to know which version a level file is saved in, the first byte of a level file is a numeric value denoting the version of the level format.

In the PC version each corresponding game version for each format version is shown, with pre-release beta revisions being referred to as "old_level". These are all revisions that occurred before the game's official 1.0 release.

1.  Beta 1
2.  Beta 2
3.  Beta 3
4.  Beta 4
5.  Beta 5
6.  Beta 6
7.  Beta 7
8.  Beta 8
9.  Beta 9
10. Beta 10
11. Beta 11
12. Beta 12
13. Beta 13
14. Beta 14
15. 1.0
16. 1.1.6
17. 1.1.7
18. 1.2
19. 1.2.1
20. 1.2.2
21. 1.2.3
22. 1.2.4
23. 1.3.0.1
24. 1.3.0.2
25. 1.3.0.3
26. 1.4
27. 1.4.0.2
28. 1.5
29. 1.5.1

Principia is supposed to have backwards compatibility with old levels, containing compatibility code to load level versions as far back as Beta 5 (used for the Smiley Man level, oldest currently available level). However during certain updates there has been minor changes to existing gameplay functionality leading to issues trying to play older levels.