# Flutter

Flutter is Google's UI toolkit for building beautiful, natively compiled applications for mobile, web, desktop, and embedded devices from a single codebase.

Focus on mobile.

[website](https://flutter.dev/)

# Getting Started

## System requirements

- bash
- curl
- file
- git 2.x
- mkdir
- rm
- unzip
- which
- xz-utils
- zip

Shared libraries: Flutter test command depends on this library being available in your environment.
- libGLU.so.1 - provided by mesa packages such as libglu1-mesa on Ubuntu/Debian and mesa-libGLU on Fedora.


## Installing

```term
sudo snap install flutter --classic
```

## Flutter doctor
Run the following command to see if there are any dependencies you need to install to complete the setup (for verbose output, add the -v flag):

```term
flutter doctor
```

## Update your path

These instructions require administrator privileges:

1. Determine the path of your clone of the Flutter SDK.
1. Locate the etc directory at the root of the system, and open the profile file with root privileges.
```term
sudo vim /etc/profile
```
1. Update the PATH string with the location of your Flutter SDK directory.
```term
if [ "`id -u`" -eq 0 ]; then
   PATH="..."
else
   PATH="/usr/local/bin:...:[PATH_OF_FLUTTER_GIT_DIRECTORY]/bin"
fi
export PATH
```
1. End the current session or reboot your system.
1. Once you start a new session, verify that the flutter command is available by running:
```term
 which flutter
```

# Android development

> Note: Flutter relies on a full installation of Android Studio to supply its Android platform dependencies. However, you can write your Flutter apps in a number of editors; a later step discusses that.

## Install Android Studio

1. Download and install [Android Studio](https://developer.android.com/studio).
1. Start Android Studio, and go through the ‘Android Studio Setup Wizard’. This installs the latest Android SDK, Android SDK Command-line Tools, and Android SDK Build-Tools, which are required by Flutter when developing for Android.
1. Run `flutter doctor` to confirm that Flutter has located your installation of Android Studio. If Flutter cannot locate it, run `flutter config --android-studio-dir <directory>` to set the directory that Android Studio is installed to.

## Set up your Android device

To prepare to run and test your Flutter app on an Android device, you need an Android device running Android 4.1 (API level 16) or higher.

1. Enable **Developer options** and **USB debugging** on your device. Detailed instructions are available in the [Android documentation](https://developer.android.com/studio/debug/dev-options).
1. Using a USB cable, plug your phone into your computer. If prompted on your device, authorize your computer to access your device.
1. In the terminal, run the `flutter devices` command to verify that Flutter recognizes your connected Android device. By default, Flutter uses the version of the Android SDK where your `adb` tool is based. If you want Flutter to use a different installation of the Android SDK, you must set the `ANDROID_SDK_ROOT` environment variable to that installation directory.

## Set up the Android emulator

To prepare to run and test your Flutter app on the Android emulator, follow these steps:

1. Enable [VM acceleration](https://developer.android.com/studio/run/emulator-acceleration) on your machine.
1. Launch **Android Studio**, click the **AVD Manager** icon, and select **Create Virtual Device**…
	- In older versions of Android Studio, you should instead launch **Android Studio > Tools > Android > AVD Manager** and select **Create Virtual Device**…. (The **Android** submenu is only present when inside an Android project.)
	- If you do not have a project open, you can choose **Configure > AVD Manager** and select **Create Virtual Device**…
1. Choose a device definition and select **Next**.
1. Select one or more system images for the Android versions you want to emulate, and select **Next**. An x86 or x86_64 image is recommended.
1. Under Emulated Performance, select **Hardware - GLES 2.0** to enable [hardware acceleration](https://developer.android.com/studio/run/emulator-acceleration).
1. Verify the AVD configuration is correct, and select **Finish**.
For details on the above steps, see [Managing AVDs](https://developer.android.com/studio/run/managing-avds).
1. In Android Virtual Device Manager, click **Run** in the toolbar. The emulator starts up and displays the default canvas for your selected OS version and device.

## Agree to Android Licenses

Before you can use Flutter, you must agree to the licenses of the Android SDK platform. This step should be done after you have installed the tools listed above.

1. Make sure that you have a version of Java 8 installed and that your `JAVA_HOME` environment variable is set to the JDK’s folder.
	Android Studio versions 2.2 and higher come with a JDK, so this should already be done.
1. Open an elevated console window and run the following command to begin signing licenses.
```term
 flutter doctor --android-licenses
```
1. Review the terms of each license carefully before agreeing to them.
1. Once you are done agreeing with licenses, run `flutter doctor` again to confirm that you are ready to use Flutter.

