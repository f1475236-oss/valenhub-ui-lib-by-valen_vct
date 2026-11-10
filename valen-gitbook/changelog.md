# Changelog

## 1.1.4

**Fixes**
* One failing animation no longer freezes scrolling and the tab indicator.
* Changing the effect while the window is minimized no longer throws errors.
* Folding and unfolding cards always restores text correctly (locked rows stay dimmed).
* Multi-select `List` now restores from configs.
* Clearing a `Keybind` to None is now saved.
* Removed or hidden controls no longer show up in search and the tab preview.
* Two controls (or cards) with the same name no longer share one saved value.
* While picking a keybind, other hotkeys (including `ToggleKey`) don't fire.
* `DiscordCard` hides the Join button until it has a valid invite.
* Negative numbers in `Stat` show correctly; `Sparkline` no longer errors with a non-whole `Step`.
* `Slider` / `Number` handle `Step = 0` or `Min > Max` safely.

**Changes**
* `ToggleKey` also accepts a string, e.g. `"K"`.
* `Keybind:Get()` returns `false` (not `nil`) when no key is set.

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
