This page contains various frequently asked questions about the game Principia, or the community site (sometimes referred to as principia-web).

[toc]

## What is principia-web?
Back in late 2020, ROllerozxa launched a new unofficial community site called principia-web, making it possible to easily share your levels again after the official community site had shut down. It's later expanded into including a forum and this wiki. It is now considered to be the primary community site with the open source release, with the levels from the old community site provided as an archive.

In January of 2025, ROllerozxa [wrote a blog post](https://voxelmanip.se/2025/01/09/the-story-of-principia-web/) going over the story of how principia-web came to be and what it has turned into, in a lot greater detail.

## What is Principia Discord?
It's the "official" Principia Discord server, [principia-web.se/discord](/discord) serves as a permalink to the invite for it. It was originally started sometime 2017 as an unofficial server, but quickly turned into the main community hub after the official community site shut down. It was originally run by uni(valence) but has been taken over by ROllerozxa after a while of administering it. It is now the primary place for Principia-related chit chat, with even sdac joining it alongside the source code release.

The main channels of the Discord server are also bridged to the [Principia Matrix space](/matrix), for those who wish to not use Discord as a platform.

## So Principia is open source now?
Yes, sdac came back and released the source code in August 2022. It is [available on GitHub](https://github.com/Bithack/principia/), and is continuing development as an open source project.

Being licensed under the BSD 3-Clause license, it is both open source and Free in that you have the freedom to use, modify and share the game and its source code.

## When is Principia coming onto Google Play?
Unlikely to happen anytime in the future. However, the Android version of Principia [is available for F-Droid](https://f-droid.org/en/packages/com.bithack.principia/), an alternative app store focusing on free and open source software.

## What about Steam?
Unlikely to happen anytime in the future. While Principia was accepted onto Steam through Steam Greenlight in 2014, it happened right when the game was abandoned and the game never ended up being released onto Steam. Steam Greenlight has since stopped existing many years ago and the Steam product page for Principia is gone, so it's not as simple as just uploading a copy of the game.

## What about iOS?
Unlikely to happen anytime in the future. See [#85](https://github.com/Bithack/principia/issues/85).

## What about macOS?
An experimental port is available for macOS, see [the download page](/download#macos). It is very incomplete and needs testing and other assistance from someone who has Apple hardware. Contributions are very welcome.

## What about [Insert platform]?
Seeing Principia on a new platform is always interesting, no matter how niche or esoteric it may be. Unless the port requires serious amount of changes to the codebase that disrupts other platforms, upstreaming support is also welcome. For prospective contributors wishing to port Principia to a new platform, you can see the [[Porting Principia]] page.

## What about [Linux distribution]?
Packaging Principia for your favourite Linux distribution or package method is very welcome, details on how to package Principia can be seen on the [[Information for Downstream Packagers]] page which should make the packaging process straightforward.

Let us know when you've done it so the package can be added to the downloads page.

## Why does my Antivirus/Windows say Principia is malicious?
Because we do not have the money for a signing certificate (which costs a lot of $$$, recurring per year). Principia is not malware, and the builds available on the [download page](/download) are built from source by [Github Workflows](https://github.com/Bithack/principia/actions).

The Windows installer is generally more likely to throw false positives than the portable version. If you are paranoid then you can download the portable version, extract it and scan the extracted game executable `principia.exe` which should give no results. The portable version can then be configured to become the exact same as an installed version of the game if you wish. See the [[Windows Portable]] page for more information.

## Where are my old levels?
They are available in the [Community Site Archive](https://archive.principia-web.se).

## Who is ROllerozxa?
He is the current Principia project maintainer, he also runs this community site and the Principia Discord server. Prior to the open sourcing he has also done various archival efforts of Principia such as archiving old game versions or old community levels. Despite his nationality and seemingly endless knowledge, he is not or has been part of Bithack, but is a community member going back to the 2013 days. You can read more about him [on his website](https://voxelmanip.se/about/).

## I forgot my password.
Please see the [Forgot password](https://principia-web.se/forgotpassword) page. Currently the process of requesting a password reset by email is manual as we don't currently have a way of automatically sending emails from the server, but requests are aimed to be responded to as quickly as possible.

## How are passwords stored?
Passwords are stored salted and hashed using the industry standard [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) hashing algorithm. It is a one-way hash algorithm and the hash that is stored in the database cannot be easily reversed, only compared against when you input the password again when logging in.

## Why is there a maximum password length limit?
The maximum length of input for the bcrypt hashing algorithm is 72 bytes, and anything beyond that is truncated. The current maximum limit of 64 characters is slightly below that just to be safe.

Generally speaking, bcrypt is an algorithm that is designed to be expensive enough to calculate that brute force attacks against the hash directly are slowed down significantly. If you have a randomly generated alphanumeric password of any sizable length, it should be practically be uncrackable within your lifetime.

## How are level screenshots/thumbnails taken?
Currently every level has one thumbnail, which is taken at the first [[Cam Marker]] (or the last camera position) at publish. The screenshots should be taken automatically on level upload after at most a minute or two. If something goes wrong with the automatic screenshotter please contact ROllerozxa.
