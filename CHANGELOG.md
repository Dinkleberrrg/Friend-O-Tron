# Changelog OctoWoW – Friend-O-Tron

> Branch `octowow` = Stand aus Henrys Installation „OctoWoW – HD Upgrade“ (WoW 1.12). Eigene Anpassungen sind im Code mit `-- [patch]` markiert.

**Basis:** refaim/Friend-O-Tron `70b9e11` (2025-12-21)

## Änderungen

### src/Database.lua – Absturz auf neuem Realm behoben
Der Eintrag `realmToEvents[GetRealmName()]` wurde nur angelegt, wenn die gesamte SavedVariable fehlte. `LoadFriends()` und `AddEvent()` greifen aber ohne nil-Prüfung darauf zu, was auf jedem Realm ohne bestehenden Eintrag zu einem Lua-Fehler führte. Tabelle und Realm-Eintrag werden jetzt jeweils einzeln angelegt, falls sie fehlen.
