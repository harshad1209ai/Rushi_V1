# RUSHI AI V2 – Android Studio starter

## What this project contains
- Native Android Java starter app and basic assistant UI.
- Text-to-speech replies using Android TTS.
- Speech input through Android SpeechRecognizer (offline preference requested on Android 13+, but actual offline availability depends on installed speech services/language packs).
- Flashlight toggle using CameraManager.
- Wi-Fi settings shortcut and Bluetooth control panel/settings shortcut.
- Camera launch.
- Safe call flow using ACTION_DIAL (does not silently place calls).
- LocalAiEngine integration boundary for a real offline LLM.

## Important: this is not yet a complete ChatGPT-level offline AI
No large language model weights are bundled. A capable local model can occupy multiple GB and performance depends on device RAM, chipset, storage and thermal limits. The next engineering step is integrating a compatible inference runtime (for example llama.cpp with a suitable quantized GGUF model) and selecting a model that the target phone can actually run.

## Build
1. Open this folder in Android Studio (current stable).
2. Allow Gradle sync; use JDK 17.
3. Install Android SDK Platform 35 and Build Tools as prompted.
4. Build > Build Bundle(s) / APK(s) > Build APK(s).

No Gradle wrapper is included; Android Studio can sync using its configured Gradle installation. For command-line builds, generate a wrapper from Android Studio/Gradle.

## Source APK limitations
The provided V1 file was an APK, not an Android Studio source project. APKs contain compiled DEX bytecode, a compiled manifest and packaged resources. They do not preserve the original Kotlin/Java source, comments, Gradle files, project structure, signing configuration or model assets. This V2 starter is therefore a clean project scaffold, not a guaranteed in-place upgrade or exact recreation of V1. The original V1 source ZIP is still required to preserve its existing screens and functionality accurately.

## Android platform limitations
- Wi-Fi direct on/off is restricted for ordinary apps on modern Android; this app opens system settings.
- Bluetooth uses the system panel/settings rather than bypassing user controls.
- Calls open the dialer for user confirmation. Ending calls programmatically generally requires default-dialer role or privileged/system permissions.
- Always-on wake-word detection is not implemented in this starter; it needs a dedicated low-power wake-word engine, foreground service, microphone permission and battery testing.
- Speech recognition and TTS offline operation depends on Android speech/TTS services and downloaded language packs.
- Camera image understanding/OCR, PDF reader, robust math solver, chat memory and the full offline LLM are planned integration modules, not yet implemented.

## Recommended next input
Provide the phone's exact model, RAM and Android version, plus the original V1 Android Studio ZIP if available. This is necessary to choose a practical quantized model and preserve V1.
