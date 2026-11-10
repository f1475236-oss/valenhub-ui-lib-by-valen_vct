# Window methods

| Method | Does |
| --- | --- |
| `:Tab(name, icon)` | Add a tab, returns it. |
| `:Group(name)` | Heading in the tab menu. |
| `:Select(tab)` | Open a tab. |
| `:Notify(cfg)` | Notification (see [Notifications](notifications.md)). |
| `:Toast(text)` | Small transient message. |
| `:Popup(cfg)` | Blocking confirm dialog. |
| `:SetAccent(color)` | Change the accent at runtime. |
| `:SetEffect(name)` | Background effect — see `Library.Effects`. |
| `:SetVisible(bool)` | Show / hide the window. |
| `:SetLayout("Side" / "Top")` | Where the tab menu sits. |
| `:SetUIScale(n)` | Scale the whole window (e.g. 0.9, 1, 1.1). |
| `:SetFont(name)` | Change the whole UI font — see [Fonts](../advanced/fonts.md). |
| `:SetTextScale(n)` | Scale only the text — see [Accessibility](../advanced/accessibility.md). |
| `:SetHighContrast(bool)` | High-contrast mode. |
| `:SetLanguage("en" / "th")` | Switch language (uses your `Translations`). |
| `:SetStatus({Map=, Detail=})` | Text in the header status line. |
| `:Tag({Text=, Color=})` | Small badge on the window. |
| `:SetKeybindList(bool)` | Show the floating keybind card. |
| `:SetLiteAnimations(bool / nil)` | Force light (`true`) or full (`false`) open/close animation; `nil` = auto. |
| `:OnUnload(fn)` | Run fn when the hub is destroyed. |
| `:Destroy()` | Remove the UI completely. |

Read `Window.Unloaded` in your loops to stop them when the hub closes.

## Library fields

| Field | Description |
| --- | --- |
| `Library.Version` | Version string, e.g. `"1.1.4"`. |
| `Library.IconURL` | Set before `CreateWindow` to load extra Lucide icons from your own host. Icons are cached in `ValenUI/cache/` after the first load. |
| `Library.Windows` | Windows currently open from this copy of the library. |
