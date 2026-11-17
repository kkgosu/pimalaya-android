---
cairn: log
change: drop-root-ide-setup
landed: 2026-11-16
---

# Open the Android project directly

At the user's request, removed the two shared root-level .run configurations and the locally added root .idea/gradle.xml. Restored the root module registration to its pre-task state. CONTRIBUTING.md now directs developers to open android/ directly and use the app module's standard Android run configuration. The Gradle wrapper, installed Windows prerequisites, local SDK location and successful debug build outputs remain; application code is unchanged. CHANGELOG.md no longer advertises shared configurations.

Validation: checked removal of the root configurations, preservation of the wrapper and nested Gradle settings, and whitespace correctness. Android Studio import and device launch were not exercised; no rebuild was needed for removing root-only IDE metadata. Previous log entries remain historical records, not current setup instructions.

Capability moved: development (Android Studio debug build on Windows, modified).
