As Principia is an open source project, all our source code is publicly available in Git repositories, not just the source code for the game but also associated infrastructure such as principia-web.

Currently our canonical source for contribution is Github, but we maintain mirrors on Codeberg for most of our repositories. They are read-only right now but should be able to contribute from Codeberg sometime in the future.

## Repositories
This is a list of all "officially" maintained repositories and their Github and Codeberg URLs, if applicable.

| Repository                | Description                             | Github                                                                                    | Codeberg                                                                                  |
| ------------------------- | --------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `principia`               | Principia game source code              | [Bithack/principia](https://github.com/Bithack/principia)                                 | [principia/principia](https://codeberg.org/principia/principia)                           |
| `android-deps`            | Dependency buildscripts for Android     | [principia-game/android-deps](https://github.com/principia-game/android-deps)             | [principia/principia-android-deps](https://codeberg.org/principia/principia-android-deps) |
| `linux-deps`              | Dependency buildscripts for Linux       | [principia-game/linux-deps](https://github.com/principia-game/linux-deps)                 | N/A                                                                                       |
| `windows-deps`            | Dependency buildscripts for Windows     | [principia-game/windows-deps](https://github.com/principia-game/windows-deps)             | N/A                                                                                       |
| `principia-utils`         | Misc. util programs for Principia       | [principia-game/principia-utils](https://github.com/principia-game/principia-utils)       | [principia/principia-utils](https://codeberg.org/principia/principia-utils)               |
| `screenshotter-container` | Docker container for screenshot build   | [principia-game/screenshotter](https://github.com/principia-game/screenshotter-container) | N/A                                                                                       |
| `principia-web`           | Source code for principia-web.se        | [principia-game/principia-web](https://github.com/principia-game/principia-web)           | [principia/principia-web](https://codeberg.org/principia/principia-web)                   |
| `wiki`                    | Content for the Wiki                    | [principia-game/wiki](https://github.com/principia-game/wiki)                             | [principia/wiki](https://codeberg.org/principia/wiki)                                     |
| `news`                    | Repository for news articles            | [principia-game/news](https://github.com/principia-game/news)                             | [principia/news](https://codeberg.org/principia/news)                                     |
| `companion-bot`           | Companion bot for the Principia Discord | [principia-game/companion-bot](https://github.com/principia-game/companion-bot)           | [principia/companion-bot](https://codeberg.org/principia/companion-bot)                   |

## Mirroring to Codeberg
Git has the ability to push to several URLs for a single remote which can be used for mirroring the repositories. For example these lines of code in `.git/config` will push principia-web to the two specified URLs:

```conf
[remote "origin"]
	url = git@github.com:principia-game/principia-web
	fetch = +refs/heads/*:refs/remotes/origin/*
	pushurl = git@codeberg.org:principia/principia-web
	pushurl = git@github.com:principia-game/principia-web
```

When making changes and committing locally simply `git push` will push the commits to both remotes automatically. To update the mirror from changes in a PR merged on Github, just `git pull` locally and then `git push` to make new commits propagate to Codeberg.
