---
cairn: change
id: windows-android-studio-build
status: landed
created: 2026-11-16
---

# Build and run from Android Studio on Windows

## Why

The repository root is open as a plain IDE project. The Gradle build lives in android/, has no wrapper, and has not been linked to the IDE. This workstation has no Rust toolchain on PATH and lacks the pinned Android build-tools and NDK, so adding a run configuration alone cannot build the application.

## What

- Add a Gradle wrapper compatible with Android Gradle Plugin 8.13.2, with the official distribution checksum.
- Add shared Android Studio configurations for building the debug APK and running the default launcher activity.
- Link android/ to the currently open root project through local, ignored IDE settings; keep SDK paths and machine-specific settings out of version control.
- Install missing Windows build prerequisites after permission: compatible Gradle, Rust stable (at least 1.89), cargo-ndk, four Android Rust targets, Android build-tools 36.1.0 and NDK 29.0.14206865. Install Microsoft C++ build tools only if needed by the Rust host toolchain.
- Document opening/syncing the Android project and the Windows prerequisites in CONTRIBUTING.md.
- Verify :app:assembleDebug on Windows. Attempt the existing unit-test command and report the existing Nix-only host SQLite requirement honestly; do not bypass or weaken it.

## Scope and limits

No app behaviour, release signing, dependency upgrades, UI changes, new build orchestration scripts or Windows port of the native SQLite test harness. Existing Linux/Nix build commands remain supported. Tool installation may require substantial downloads, an elevation prompt, and an IDE restart. If Windows-specific source changes prove necessary, stop and review their scope before proceeding.
