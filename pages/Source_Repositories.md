As Principia is an open source project, all our source code is publicly available in Git repositories, not just the source code for the game but also associated infrastructure such as principia-web.

Currently our canonical source for contribution is Github, but we maintain mirrors on Codeberg for most of our repositories. They are read-only right now but should be able to contribute from Codeberg sometime in the future.

## Repositories
This is a list of all "officially" maintained repositories and their Github and Codeberg URLs, if applicable.

| Repository               | Description                              | Github                                                   | Codeberg                                              |
| ------------------------ | ---------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------- |
| `principia`              | Principia game source code               | https://github.com/Bithack/principia                     | https://codeberg.org/principia/principia              |
| `principia-android-deps` | Dependency buildscripts for Android      | https://github.com/principia-game/principia-android-deps | https://codeberg.org/principia/principia-android-deps |
| `principia-utils`        | Misc. util programs for Principia        | https://github.com/principia-game/principia-utils        | N/A                                                   |
| `principia-web`          | Source code for principia-web.se         | https://github.com/principia-game/principia-web          | https://codeberg.org/principia/principia-web          |
| `principia-web-archive`  | Source code for archive.principia-web.se | https://github.com/principia-game/principia-web-archive  | https://codeberg.org/principia/principia-web-archive  |
| `wiki`                   | Content for the Wiki                     | https://github.com/principia-game/wiki                   | https://codeberg.org/principia/wiki                   |
| `news`                   | Repository for news articles             | https://github.com/principia-game/news                   | N/A                                                   |
| `companion-bot`          | Companion bot for the Principia Discord  | https://github.com/principia-game/companion-bot          | N/A                                                   |
| `image-to-lua`           | Convert images into Principia Lua code   | https://github.com/principia-game/image-to-lua           | N/A                                                   |

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
