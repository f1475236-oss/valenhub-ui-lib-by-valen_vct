# Changelog

## 1.1.0

**Safer for hubs**
* Running two hubs that both use Valen UI no longer breaks either one (keybinds, dragging and windows stay independent).
* Every hub keeps its own files in `ValenUI/<Id>/`. Add `Id` to `CreateWindow`.
* Re-running the same hub replaces the old window cleanly.
* Language, font, UI size and auto-load now persist between runs (they were being lost on reload).

**Configs**
* `LoadConfig(name, { Silent = true })` and `ImportConfig(code, { Silent = true })` restore values without firing callbacks.
* `ConfigVersion` + `MigrateConfig` to upgrade old saves.
* Renaming a tab or card no longer wipes users' settings when the control name is unique.
* Old configs from 1.0 still load.

**Performance**
* Smoother open / close / minimize on big hubs (`LiteAnimations`, automatic above 80 controls).
* Folding a card with many controls no longer stutters; folded cards stop rendering.
* Icons load in the background and are cached — no freeze on startup.

**Other**
* `Library.Version`, `Library.IconURL`.
* Callback errors print a full traceback.
