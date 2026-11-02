# Theming & overrides

Distributors can rebrand the whole window from `CreateWindow` without touching the library. Pass a font, a theme table, or an accent.

```lua
Library:CreateWindow({
    Title = "My Hub",
    Font = "rbxasset://fonts/families/GothamSSm.json",  -- any font family
    Accent = Color3.fromRGB(90, 200, 255),
    Theme = {                                   -- override any token
        Base = Color3.fromRGB(13, 13, 15),
        Card = Color3.fromRGB(20, 20, 24),
        Text = Color3.fromRGB(230, 230, 235),
    },
})
```

Read the current theme from `Library.Theme` and the available background effects from `Library.Effects`. Register extra themes with `Library:AddTheme(name, table)`.

{% hint style="info" %}
**Keep it yours.** Only the tokens you pass are overridden; everything else falls back to the Valen defaults, so partial themes are safe.
{% endhint %}
