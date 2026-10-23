# Migraine Daily Life Coach — Bangladesh Edition

Owner / creator shown in About and Settings: **MD সাকিব হোসাইন নীরব**. The name is fixed in the app source and is not editable through ordinary user profiles.

## Included features
- Migraine diary with date, severity, notes, symptom checkboxes and possible-trigger checkboxes
- Daily routine checklist
- Daily water-glass tracker
- Bengali/English language preference control
- Bangladesh edition About and Settings owner identity
- Initial owner password setup, authenticated password change, PBKDF2-HMAC-SHA256 password verifier with random salt

## Security limits
The owner password is not hardcoded and is never shown in source. This implementation stores a salted PBKDF2 verifier in app-private SharedPreferences. It is local-device protection only: someone who modifies/repackages the app or controls the device may bypass it. There is deliberately no public password reset/bypass. For security across shared copies/devices, use a backend authentication service and server-side owner authorization. Do not use this local-only build as proof of strong owner identity.

## Six numbered build steps

1. **Get the complete source project:** download `MigraineDailyLifeCoach-Bangladesh-source.zip` from this conversation and extract it. The zip contains the Gradle project and Kotlin source.
2. **Install build tools:** install Android Studio with Android SDK Platform 35 and a compatible JDK (Android Studio's bundled JDK is suitable). Open the extracted project and allow Gradle sync.
3. **Resolve dependencies:** in Android Studio choose Sync Project with Gradle Files, or from the project root run `./gradlew` after adding a Gradle wrapper. Android Studio can build without a wrapper file.
4. **Build the APK — this is the actual build step:** in Android Studio choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**, or from a configured terminal run `gradle :app:assembleDebug`. A release APK can be built with `gradle :app:assembleRelease`.
5. **Find the generated APK:** debug output is `app/build/outputs/apk/debug/app-debug.apk`; release output is `app/build/outputs/apk/release/app-release-unsigned.apk` unless you configure signing. The APK does not exist until Step 4 finishes successfully. Verify the file appears before sharing it.
6. **Install/share from an Android phone:** easiest computer-free option is use an Android IDE/build environment that supports Gradle/Android SDK (for example a compatible cloud build workflow) to build the project, then download the resulting APK to the phone. In Files/Downloads tap the APK and allow “Install unknown apps” for that file manager if Android asks. To share, use Files > long-press the APK > Share, then choose Bluetooth, Quick Share, email or messaging. Do not use `adb` unless a computer/ADB environment is available.

## Build notes
- Android package: `com.sisir.migrainedailylifecoach`
- Minimum Android version: Android 8.0 (API 26)
- This project is source code only; no APK is bundled or claimed to have been generated here.
- For a signed distributable release, configure a signing key securely in Android Studio. Never commit the signing key or passwords into source control.
