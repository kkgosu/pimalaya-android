---
cairn: spec
capability: development
status: current
---

# Development

### Requirement: Android Studio debug build on Windows

The repository SHALL provide a checksummed Gradle wrapper in android/ to assemble the debug APK. Documentation SHALL name the Windows JDK, Android SDK/NDK and Rust prerequisites and direct developers to open android/ as the Android Studio project, using its app module. No shared root-level run configurations or root-level Gradle linking SHALL be required. Machine-specific SDK and IDE paths SHALL remain untracked. Existing native unit-test safeguards SHALL not be disabled to make a Windows build appear verified.

#### Scenario: Build from Android Studio

- GIVEN Windows with the documented prerequisites installed and android/ opened in Android Studio
- WHEN the developer builds the app module's debug variant
- THEN Gradle cross-compiles the existing Rust bridge and assembles the debug APK.
