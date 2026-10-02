# Changelog OctoWoW – Friend-O-Tron

> Branch `octowow` = the state from Dinkleberrrg's "OctoWoW – HD Upgrade" install (WoW 1.12). Own changes are marked with `-- [patch]` in the code.

**Base:** refaim/Friend-O-Tron `70b9e11` (2025-12-21)

## Changes

### src/Database.lua – crash on a new realm fixed
The entry `realmToEvents[GetRealmName()]` was only created when the whole SavedVariable was missing. `LoadFriends()` and `AddEvent()` index it without a nil check, which raised a Lua error on every realm without an existing entry. The table and the realm entry are now each created on their own if missing.
