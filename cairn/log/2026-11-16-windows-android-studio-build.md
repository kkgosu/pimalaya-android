---
cairn: log
change: windows-android-studio-build
landed: 2026-11-16
---

# Windows debug build and IDE configurations

Added the Gradle 8.13 wrapper, pinned to the official distribution SHA-256, and shared root-level Android Studio configurations: Build Debug APK runs :app:assembleDebug in android/, and Pimalaya Debug builds and launches the app's default activity. CONTRIBUTING.md documents Windows prerequisites, importing the nested build, JDK 17 selection, environment variables, output paths and the unchanged Nix-only store-test requirements. CHANGELOG.md records the development tooling addition.

On the requesting workstation, installed Rust stable with the four Android targets, cargo-ndk 4.1.2, Temurin JDK 17, Microsoft C++ Build Tools, Android build-tools 36.1.0 and NDK 29.0.14206865. Set user JAVA_HOME and ANDROID_HOME; local SDK and Gradle-link settings remain ignored. Android Studio must restart to inherit the installed tools, then sync the nested Gradle project.

Validation: the generated wrapper successfully ran :app:assembleDebug on Windows, including cargo-ndk release builds for all four ABIs. APKs are under android/app/build/outputs/apk/debug/, including app-universal-debug.apk. The required Nix unit-test command could not run because nix is unavailable; the existing host SQLite harness was not ported or bypassed. IDE import, installation and activity launch were not exercised, and no device UI was driven.

Capability moved: development (Android Studio debug build on Windows, added).
