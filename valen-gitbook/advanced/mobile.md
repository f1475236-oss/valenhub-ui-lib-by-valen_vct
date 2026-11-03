---
description: Valen UI works with touch out of the box.
---

# Mobile

Valen UI is built for touch as well as mouse. Everything a desktop user can do, a mobile user can too — no separate code path.

## What works on touch

* **Every control** — toggles, sliders, dropdowns, inputs, keybinds, color pickers, lists — responds to taps and drags.
* **Dragging cards** out of the window, **pinning** them, and **reordering** them all work with a finger. A card returns to its original slot when you drop it back inside.
* **Tap a card header** to collapse or expand it.
* **Dragging the window** by its title bar.
* The **toggle key** also has an on-screen button on mobile, so users without a keyboard can still show and hide the hub.

## Tips for mobile-friendly hubs

* Keep **two columns** of sections — they stack and scroll cleanly on a phone.
* Prefer **Segmented** and **Dropdown** over long rows of buttons; they're easier to tap.
* Use [UI size](../window/methods.md) (`SetUIScale`) and [Text scale](accessibility.md) so users can size the hub to their screen.

```lua
-- let mobile users scale the hub down to fit
Settings:Segmented({
    Name = "UI size",
    Options = { "S", "M", "L" },
    Default = "M",
    NoSave = true,
    Callback = function(v) Window:SetUIScale(v == "S" and 0.85 or v == "L" and 1.15 or 1) end,
})
```

{% hint style="info" %}
Nothing special is required to "enable" mobile — it's always on. Just design with tap targets in mind.
{% endhint %}
