# local_auth_bug

> A minimal complete reproducible code sample for https://github.com/flutter/flutter/issues/64996

## Description

I am using local_auth to sign in with fingerprint and encounter some problem with Android. When I run in debug mode, it works fine. However, if I build it in app-bundle/apk in release mode `--release`, the app crashing before the popup to ask for fingerprint.

## Step to reproduce

Try to `flutter build apk` and `flutter install` on an Android device, you'll encounter the crash after the apps loaded.

## Issue

Update android gradle plugin.

- When I opened this project in Android studio, I saw this `Plugin Update Recommended` popup.

![image](./screenshots/local_auth_bug.png)

- After I updated the plugin, this is the changes; (`android/build.gradle`).

![image](./screenshots/update_plugin.png)

- Encounter the issue.

## Workaround for this issue

Change to `classpath 'com.android.tools.build:gradle:3.5.0'` in `android/build.gradle` .




