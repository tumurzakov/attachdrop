Attachdrop
==========

AwesomeWM Quake like windows management

Based on [Stratchpad](https://awesome.naquadah.org/wiki/Scratchpad_manager)

Show/hide windows by pressing Mod + < key >

Features
--------

* Run/Hide/Show program by pressing Mod + < key >
* Attach any window to custom key by Ctrl + Mod + < key >

Installation
------------
* Clone this project to your AwesomeWM config folder
* Insert into rc.lua code
```
local drop = require("attachdrop")

globalkeys = awful.util.table.join(
    -- attach terminal to `
    awful.key({ modkey,           }, "`", function () drop.toggle("terminator --profile=POP", "left", "top", 0.8, 0.8) end),
    -- after reload awesomewm losses all drop windows so they must be reattached
    awful.key({ modkey, "Control" }, "`", function () drop.attach("terminator --profile=POP") end),

    -- add three custom keys a, s, d to attach arbitary window
    awful.key({ modkey,           }, "a", function () drop.toggle("custom1", "left", "top", 0.95, 0.95) end),
    awful.key({ modkey, "Control" }, "a", function () drop.attach("custom1") end),
    awful.key({ modkey,           }, "s", function () drop.toggle("custom2", "left", "top", 0.95, 0.95) end),
    awful.key({ modkey, "Control" }, "s", function () drop.attach("custom2") end),
    awful.key({ modkey,           }, "d", function () drop.toggle("custom3", "left", "top", 0.95, 0.95) end),
    awful.key({ modkey, "Control" }, "d", function () drop.attach("custom3") end),
)

```

