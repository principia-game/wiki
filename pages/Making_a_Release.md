This page details notes for releasing a new Principia version.

[toc]

## Preparation
First of all, make sure that Principia runs on the three major supported platforms first: Windows, Linux and Android. It is assumed that all of them successfully build as the CI will test this for every commit, but be sure to test them on real hardware so that no breaking bugs or regressions have cropped up. Download the latest CI artifacts on the master branch for each platform and make sure that they work well.

- **Windows**: Be sure to test the installer binary on Windows 10. Run through the installer, see such that it runs, can make connections to principia-web (i.e. cURL and encryption works), and does not crash when opening GTK3 dialogs.
- **Linux**: Test the AppImage on a couple different distro branches, old and new.
- **Android**: Test that it runs, play some level and such.

Also update the changelog on the wiki beforehand so that it is up to date with the changes in the new release, and write a Fastlane changelog metadata for the F-Droid version (you need to do this before tagging a release!).

## Incrementing version & tagging
To increment the version, the script `set_version.lua` found in the `utils/` folder in the source tree should be used. It will update the version across the entire codebase at once reducing human error. Simply run it with `luajit ./utils/set_version.lua` and input the new version code and version name. When done, review the changes it has done and commit it.

When pushed, go onto the Github repository and [draft a new release](https://github.com/Bithack/principia/releases/new). Input the new version's name and accompanying tag name, and create the tag pointing to master which is where the version update commit should have been pushed.

Template for release description (you can guess the news ID it will have):

```md
### [News article](https://principia-web.se/news/<NEWSID>) - [Changelog](https://principia-web.se/wiki/Changelog#<RELEASE NAME WITH DASHES>)

To download Principia see the [Download](https://principia-web.se/download) page. You can also download the binaries associated with this version below:
```

Once the release is created and tagged the CI should begin to make builds.

## Binaries
Windows, Linux and Android binaries are officially provided for each release. The CI now produces artifacts at an acceptable quality to distribute these. Look at the CI job for the abovementioned release tag and wait until all the jobs have completed and have artifacts available. Then run the `prepare_release_builds.sh` script which will download and prepare the artifacts to be uploaded to the release:

```bash
_ANDROID_KEY="(signing key)" ./utils/prepare_release_builds.sh
```

## Uploading builds and updating downloads
Builds are now hosted on GitHub and should be uploaded to the respective release. After having prepared them locally per the steps above, go to edit the release and upload the files to it.

The principia-web download page source is in the site's Git repository at `templates/download.twig`. Update the `version` variable and URLs should automatically update on the page.

## Let people know
Make a news post on principia-web. It should link to the download page as well as the changelog. The release description should also link to this news article.

Update the Principia version code on principia-web available in `internal/version-code.php` to reflect the new version code. This will make the client begin to start prompting players to update to be sure to have things finished before this.

Then make an announcement on the Discord server linking to the principia-web news article. It can be brief but just let people know it's a thing.

Make a post on the Mastodon account (run by ROllerozxa) writing a bit about the new release and link to the news article at the end. Be sure to find some nice level to use as a screenshot.

### More...
Update the [Principia itch.io listing](https://rollerozxa.itch.io/principia), copy the download links on the principia-web download page and update the URLs on itch.io as well as the version numbers.

Update the [Libregamewiki page](https://libregamewiki.org/Principia), update the version number and link to the release's news announcement.

Check in on downstream packagers for Principia, such as F-Droid and various Linux distributions. Some automatically check for tags on the Git repository while some rely on word of mouth to learn about the new update.
