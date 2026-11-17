---
cairn: log
change: remove-plain-ide-module
landed: 2026-11-16
---

# Remove the stale plain IDE module

The initial root-folder import registered pimalaya-android as a plain JAVA_MODULE. Linking android/ left that registration in place, which Android Studio refuses to compile alongside Android Gradle modules. Removed only its entry from the workstation's ignored .idea/modules.xml, preserving source files and the Gradle link. CONTRIBUTING.md now documents removing that stale registration through Studio, including the warning's removal action if the IDE retains its in-memory module state.

Validation: inspected the registered module and its JAVA_MODULE definition; checked the edited registration XML and preservation of the android/ Gradle link. No application code changed. IDE reload/sync and compilation from Studio remain for the user; the earlier Windows Gradle debug assembly remains the build evidence.

Capability moved: development (Android Studio debug build on Windows, modified).
