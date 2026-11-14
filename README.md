# RUSHI AI V1.0 — Android project

This is a native Android starter app built with Kotlin and Jetpack Compose.

## Included in this V1.0 starter
- Dark futuristic RUSHI interface
- Text chat UI
- Android speech recognition (microphone permission requested at runtime)
- Android Text-to-Speech replies
- Local demo responses

## Not connected yet
This build does **not** include a cloud AI model/API, persistent long-term memory, wake-word listening, or autonomous phone control. The assistant currently uses local demo replies. These require the next development steps and, for cloud AI, a secure backend and API credentials.

## Build an installable debug APK
1. Install Android Studio and its Android SDK (API 35) on a computer.
2. Open this project folder in Android Studio.
3. Allow Gradle sync to complete.
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Android Studio creates the debug APK at:
   `app/build/outputs/apk/debug/app-debug.apk`

Alternatively, push this project to a GitHub repository. The included GitHub Actions workflow builds the debug APK and makes it available as a workflow artifact.

## Install on Android
Download `app-debug.apk` to your phone, open it, and allow installation from that source when Android asks. Grant microphone permission when using voice input.

## Requirements
- JDK 17
- Android Gradle Plugin 8.7.3
- Android SDK Platform 35
- Android device with Android 8.0 or newer
