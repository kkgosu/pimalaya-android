---
cairn: delta
change: windows-android-studio-build
---

## ADDED Requirements

### Requirement: Android Studio debug build on Windows

The repository SHALL provide a checksummed Gradle wrapper and shared IDE configurations to assemble the debug APK and launch the default activity from the Android Gradle build. Documentation SHALL name the Windows JDK, Android SDK/NDK and Rust prerequisites. Machine-specific SDK and IDE paths SHALL remain untracked. Existing native unit-test safeguards SHALL not be disabled to make a Windows build appear verified.

#### Scenario: Build from Android Studio

- GIVEN Windows with the documented prerequisites installed and android/ imported into Android Studio
- WHEN the developer selects the shared debug build configuration
- THEN Gradle cross-compiles the existing Rust bridge and assembles the debug APK.

#### Scenario: Run the app

- GIVEN the Android Gradle project has synced and a compatible device or emulator is selected
- WHEN the developer runs the shared application configuration
- THEN Android Studio builds, installs and launches the default activity.

## MODIFIED Requirements

## REMOVED Requirements
