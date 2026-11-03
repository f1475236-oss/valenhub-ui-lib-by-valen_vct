---
description: Text size independent of UI scale, plus a high-contrast mode.
---

# Accessibility

Valen UI separates **text size** from **window size**, and offers a **high-contrast** mode — so users who need bigger or clearer text don't have to blow up the whole window.

## Text scale

`Window:SetUIScale(n)` scales the entire window (frames, padding, text together). `Window:SetTextScale(n)` scales **only the text**, leaving the layout where it is. Range `0.75`–`2`.

```lua
Window:SetTextScale(1.25)   -- 25% larger text, same window size
Window:SetTextScale(1)      -- back to normal
print(Window:GetTextScale())
```

## High contrast

`Window:SetHighContrast(true)` lifts text toward white and strengthens borders for readability.

```lua
Window:SetHighContrast(true)
Window:SetHighContrast(false)
print(Window:IsHighContrast())
```

Both settings are saved and restored automatically on the next load.

## A Settings panel

```lua
local a11y = Settings:Section("Accessibility", "Right", "accessibility")

a11y:Segmented({
    Name = "Text size",
    Options = { "A", "A+", "A++" },
    Default = "A",
    NoSave = true,
    Callback = function(v)
        Window:SetTextScale(v == "A++" and 1.4 or v == "A+" and 1.2 or 1)
    end,
})

a11y:Switch({
    Name = "High contrast",
    NoSave = true,
    Callback = function(on) Window:SetHighContrast(on) end,
})
```

{% hint style="info" %}
Apply these after the hub is fully built (e.g. from a Settings tab the user opens later). Controls added *after* a `SetTextScale` call keep their default size until you call it again.
{% endhint %}
