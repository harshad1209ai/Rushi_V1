# RUSHI AI V2.1 – Improved Android Studio project

This update is based on the V2 project found in the user's Library and retains its package/application ID (`com.rushi.ai`).

## Fixed / added in this revision
- Sending text now returns a response instead of echoing the prompt as the only behaviour.
- Offline arithmetic parser supports `+ - * / % ^`, brackets, decimals, and expressions such as `2+2`, `125*48`, `(12+8)/4`.
- Chat transcript is appended and saved locally with SharedPreferences.
- Camera button opens the installed camera app; Gallery button opens Android's image picker.
- On-device ML Kit text recognition extracts printed text from selected images and camera thumbnails. OCR runs locally after dependencies/model are available.
- Text-to-speech, speech input, flashlight, Wi-Fi/Bluetooth settings and safe dialer launch retained.

## Important limitations (not hidden)
- This is **not** an exact GPT-6 clone and does not contain a full generative LLM. `LocalAiEngine` is an honest offline fallback plus deterministic arithmetic. Unknown open-ended questions receive a clear limitation message rather than fake answers or repeated prompts.
- OCR extracts text; it does not yet understand arbitrary diagrams or solve every photographed engineering problem. Full image reasoning needs a compatible local vision-language model.
- PDF file selection/reading, wake-word (`Hey Rushi`), contact-name lookup, automatic call hang-up, and full offline knowledge base are not implemented yet.
- Wi-Fi/Bluetooth changes are delegated to Android system settings/panels. Call starts in the dialer for user review. Ending calls programmatically needs default-dialer/privileged access and is not included.
- ML Kit dependency must be downloaded during the first Gradle sync. The OCR inference itself is on-device; first build therefore needs internet.
- A real offline language model and inference runtime (e.g. llama.cpp with a quantized GGUF model) still need to be selected based on phone RAM, chipset and storage.

## Build
1. Open the `RUSHI_AI_V2_Android_Project` folder in Android Studio.
2. Use JDK 17 and Android SDK Platform 35.
3. Allow Gradle sync (internet required the first time for dependencies).
4. Build > Build Bundle(s) / APK(s) > Build APK(s).

No APK build was verified in this environment because Android SDK/Gradle build tooling is not configured here.
