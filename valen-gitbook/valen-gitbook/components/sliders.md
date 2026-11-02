# Slider & Number

A **Slider** drags across a range. A **Number** is a stepper for exact values.

```lua
sec:Slider({
    Name = "Place delay",
    Min = 0, Max = 2000, Step = 50, Default = 300,
    Suffix = "ms",
    Callback = function(v) end,
})

sec:Number({ Name = "Walk speed", Min = 16, Max = 200, Step = 1, Default = 16 })
```

**Methods:** `:Set(n)`, `:Get()`, `:SetRange(min, max)`.
