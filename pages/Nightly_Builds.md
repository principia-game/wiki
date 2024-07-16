
---

**⚠️ Disclaimer**
<br>The builds found here are **DEVELOPMENT BUILDS**, and contain changes as they are being developed. When downloading a nightly release you get the game at any point in development which may be broken or buggy at times. These nightly builds are provided for testing purposes.

---

Whenever a commit with code changes is made in the Principia source repository the game is automatically built for all platforms, and if successful it will upload the builds as artifacts.

You can see a list of all the recent runs on the [Actions](https://github.com/Bithack/principia/actions?query=branch%3Amaster) tab on the Principia Github repository. Each workflow with a green label have associated artifacts which are builds of the game for each platform you can download.

As the stable builds are taken directly from the CI when a new release is made, the packaging of the nightly builds are not much different from the stable builds.

## Latest nightly downloads
The following links use nightly.link to provide permalinks for the latest nightly build produced.

All Github Actions artifacts come inside of a zip archive even if there is only one file inside. For artifacts that already are an archive this means there are nested archives.

### Windows
- [Windows Installer, 64-bit](https://nightly.link/Bithack/principia/workflows/windows/master/principia-setup.exe.zip)
- [Windows Portable, 64-bit](https://nightly.link/Bithack/principia/workflows/windows/master/principia-portable.7z.zip)

### Android
- [Android APK, ARM & x86_64 (unsigned!)](https://nightly.link/Bithack/principia/workflows/android/master/principia-release-unsigned.apk.zip)

As the name implies the APK file is unsigned, and you will need to sign it with `apksigner` before it can be installed.

### Linux
- [Linux AppImage, 64-bit](https://nightly.link/Bithack/principia/workflows/linux/master/Principia-x86_64.AppImage.zip)

If you are on Linux you might also want to [build from source](/wiki/Compiling_Principia#linux) yourself from the latest master.

## Distinguishing nightly builds
As the version number is not incremented until a new release is made, the nightly builds will show up as the same version as the latest stable release. As a slight distinguishing mark if you click on the version number in the bottom right corner of the main menu a toast will appear with the date and time on which the build was made. This can then be used to determine what commit it was built from.
