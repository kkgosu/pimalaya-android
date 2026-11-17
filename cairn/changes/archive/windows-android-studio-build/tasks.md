---
cairn: tasks
change: windows-android-studio-build
---

- [x] Identify the missing Gradle import, configurations and workstation prerequisites.
- [x] Obtain human approval for the plan, tool installation and long-running commands.
- [x] Install missing Windows prerequisites and verify their versions through installation and successful compilation.
- [x] Add the checksummed Gradle wrapper and shared run configurations.
- [x] Link the nested Gradle build locally and document Windows setup; IDE restart/sync remains for the user.
- [x] Validate debug assembly; the Nix unit-test command is blocked by missing nix and the native host SQLite requirement, with no safeguards bypassed.
- [x] Fold the development capability into the spec, append the landing log and archive this change.
