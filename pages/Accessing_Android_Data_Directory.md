Starting with the open source version of Principia, the Android version now stores its user data in its scoped app storage at `/storage/emulated/0/Android/data/com.bithack.principia/files/`. This is caused by a restriction of recent Android API levels and Google Play policies and it is unfortunately impossible to store it in the old more accessible `/storage/emulated/0/Principia/` location.

This storage area can tend to be fragile and will be deleted when you uninstall the Principia app, so it is recommended to frequently back up this location to keep your locally saved levels safe.

In addition, if you have old saves you will need to move it manually from `Principia/` to `Android/data/com.bithack.principia/files/` to be able to access it. Follow one of these methods and then move the data from the old location to the new location.

[toc]

## Total Commander Workaround (Android 12 and below)
[Total Commander](https://play.google.com/store/apps/details?id=com.ghisler.android.TotalCommander) (and possibly other file managers) has a method to workaround the restrictions put in place by Google, by taking advantage of a bug in Android 12 and below that allows file managers to be given permission to `Android/data/`.

Navigate to `Internal shared storage > Android > data`. Press on the folder named `-> Installed apps`.

![/storage/emulated/0/Android/data/](images/android_data_1.png)

It will prompt you to grant Total Commander access to this folder. Simply press "Yes".

![total commander prompt yadda yadda](images/android_data_2.png)

It will take you to a screen that looks something like this. **Do not navigate into the Principia folder or any other one**, simply press the "Use this folder" button at the bottom.

![don't get too excited!](images/android_data_3.png)

If you get a confirmation prompt, just press the allow button.

![allow total commander to access all ur filez](images/android_data_4.png)

You should be brought to the `/Android/data` directory listing in Total Commander now. Find the `com.bithack.principia` folder and go inside the `files` folder, which is where the game's files now reside.

![success](images/android_data_5.png)

Now, you may copy over your old data and levels to this location if you want.

## Through ADB (Needs computer)
You can access the scoped storage through ADB, a debugging tool part of the [Android platform tools](https://developer.android.com/studio/releases/platform-tools). In order to use ADB, you will need to enable USB debugging from the Android developer settings and connect your phone to a computer. On Linux, it should work out of the box. However on Windows you will need to find so called "ADB drivers" from your phone's manufacturer.

ADB is primarily a command-line tool, and you usually would want to use the `adb pull` and `adb push` commands similar to working with something like SCP. ADB also supports tab auto-completion on the remote side, so you can look at the directory structure on your phone while typing out a command. Some example commands:

* **Backing up your entire Principia user data to your computer:**
  `adb pull /storage/emulated/0/Android/data/com.bithack.principia/files/ principia_backup/`

* *Alternatively if you're migrating from the old location:*
  `adb pull /storage/emulated/0/Principia/ principia_backup`

* **Restore from a backup:**
  `adb push principia_backup/* /storage/emulated/0/Android/data/com.bithack.principia/files/`

The adb shell command is also available allowing you to launch a shell on your phone, use `cd /storage/emulated/0/Android/data/com.bithack.principia/files/Principia` to navigate into the user data and manage it with regular Linux terminal commands.