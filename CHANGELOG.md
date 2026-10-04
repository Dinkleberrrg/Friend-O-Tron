# Changelog OctoWoW – Friend-O-Tron

> Branch `octowow` = the state from Dinkleberrrg's "OctoWoW – HD Upgrade" install (WoW 1.12). Own changes are marked with `-- [patch]` in the code.

**Base:** refaim/Friend-O-Tron `70b9e11` (2025-12-21)


## Releases

Version scheme: `<upstream version>-octo.<n>`. Each release is a git tag `v<version>`; older versions can be downloaded from the tag page on GitHub.

### 1.2-octo.2 – 2026-10-04
- Code comments of the changes translated to English. No functional change.

### 1.2-octo.1 – 2026-10-03
- First tagged release with the changes listed below.

## Changes

### src/Database.lua – crash on a new realm fixed
The entry `realmToEvents[GetRealmName()]` was only created when the whole SavedVariable was missing. `LoadFriends()` and `AddEvent()` index it without a nil check, which raised a Lua error on every realm without an existing entry. The table and the realm entry are now each created on their own if missing.
