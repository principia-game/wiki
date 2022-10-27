Starting with the open source version of Principia, the Android version now stores its user data in its scoped app storage at `/storage/emulated/0/Android/data/com.bithack.principia/files/`. This is caused by a restriction of recent Android API levels and Google Play policies and it is unfortunately impossible to store it in the old more accessible `/storage/emulated/0/Principia/` location.

This storage area can tend to be fragile and will be deleted when you uninstall the Principia app, so it is recommended to frequently back up this location to keep your locally saved levels safe.

In addition, if you have old saves you will need to move it manually from `Principia/` to `Android/data/com.bithack.principia/files/` to be able to access it.

## Accessing the Android Data Directory
You might be able to access the path with your favourite file manager, but not every file manager is able to access the folder, as it is heavily restricted by the Android OS.

For this tutorial [Total Commander](https://play.google.com/store/apps/details?id=com.ghisler.android.TotalCommander) will be used. It is a high-quality free and ad-free file manager app that also supports accessing the scoped Android app data folder (`/storage/emulated/0/Android/data/`).

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