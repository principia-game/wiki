This page details notes for releasing a new Principia 1.5.2 beta build.

[toc]

## Binaries
First of all, make sure that Principia runs on the three major supported platforms, with focus on Windows and Android. Linux users primarily compile from source, either with provided buildscripts or manually from source, and build out-of-band from other platforms. As most development is also done on Linux it is of lesser importance to test it when making a release (it is usually the most tested platform during development). It is however assumed that all of them successfully build, as the CI will test this for every commit.

Windows and Android binaries are provided for each release. The CI now produces artifacts at an acceptable quality to distribute these. Look at the commit on master that you would want to release on and download the CI artifacts (requires being logged into GitHub).

### Windows
The Windows action generates an x64 NSIS Windows installer as the artifact. Download it and extract the .zip archive it is contained within. The binary should be renamed `principia_1.5.2_beta_YYYY-MM-DD.exe`. The "for Windows" is implied with the file extension.

Be sure to test the installer binary on Windows 10. Run through the installer, see such that it runs, can make connections to principia-web (i.e. cURL and encryption works), and does not crash when opening GTK3 dialogs.

### Android
The Android action generates an APK as an artifact, containing armeabi-v7a and arm64 native libraries currently. Download it and extract the .zip archive it is contained within. The APK should be renamed `principia_1.5.2_beta_YYYY-MM-DD.apk`. The "for Android" is implied with the file extension.

The CI generates unsigned APK files such that they can be signed locally by a signing key. Currently ROllerozxa holds the Android signing key for 1.5.2 beta builds.

Be sure to test the APK on a real phone. Install it, start it and wander around to see that everything works.

## Uploading and updating downloads
Currently 1.5.2 beta builds are hosted by ROllerozxa on `grejer.voxelmanip.se`, but may be moved onto GitHub releases to offload bandwidth and to allow tagging beta builds. This is to be decided.

Implying `grejer.voxelmanip.se` is still being used for hosting, upload the binaries to `/srv/grejer/principia/` via rsync. Old binaries can be kept on the server for a while unless there is a good reason to remove them.

The principia-web download page source is in the site's Git repository at `templates/download.twig`. Update the download links referenced on there.

Principia is also listed on [itch.io](https://rollerozxa.itch.io/principia), and directly links to downloads hosted on `grejer.voxelmanip.se`. These should also be updated.

## Community
- Write a changelog detailing what has changed in this build from the previous one.
- Make a news post on principia-web.
- Make an announcement on the Discord server, linking to the principia-web news article.
- Make a post on the Mastodon account, linking to the principia-web news article.
