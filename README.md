# DreamShield Android v0.6.1

The native Android app pairs with the DreamShield desktop server. Its Jetpack Compose interface shows connection status, bedside temperature and humidity, snapshots, and history. It supports policy presets and sampling settings, along with a local sleep journal, nightly routines, and offline soundscapes.

## Build

Open this repository in Android Studio. The project uses Gradle 9.3.1 and Android Gradle Plugin 9.1.1. Install Android SDK Platform 37 and Build Tools 37.0.0 in SDK Manager. The app targets API 37 and supports API 29 and later. The verified Windows build used OpenJDK 23.0.2, with Java and Kotlin compilation targeting Java 17.

Build and test on Windows from the repository root.

~~~powershell
.\gradlew.bat :app:assembleDebug
.\gradlew.bat :app:testDebugUnitTest
~~~

Configure the SDK in Android Studio or through `ANDROID_HOME`. The debug APK is written to `app/build/outputs/apk/debug/`. For a signed release, configure the project's Gradle signing options with your own keystore.

## Pair with the server

1. Start [DreamShield Server](https://github.com/Reizen721/dreamshield-server) on your PC. This Android release pairs with Server v0.1.6.
2. On the PC, open [the mobile setup page](http://127.0.0.1:8016/mobile-setup).
3. Connect your phone and PC to the same local network. In the app, use the pairing information shown on the setup page. The mobile gateway uses HTTPS on port `8746` by default.

Configure the thermal assessment and closed-loop temperature control in the desktop console. See the [mobile API contract](https://github.com/Reizen721/dreamshield-server/blob/v0.1.6/docs/mobile-api.md) for pairing and policy routes, and the [compatibility matrix](https://github.com/Reizen721/dreamshield-server/blob/v0.1.6/docs/compatibility.md) for tested versions. The Apple companion app is in [DreamShield iOS](https://github.com/Reizen721/dreamshield-ios).

## Verification

The debug build and 62 unit tests passed on Windows for v0.6.1.
