---
tags: [system]
script: ServerScriptService.TreeFarmServer, StarterPlayerScripts.MachineEffects
---
# Tree Maker

- DEPOSIT LOGS feeds the machine; **3 logs = 1 tree**.
- Craft time: 2 s per tree, × 0.75 per FASTER MAKER level ([[Shop Upgrades]]).
- Finished trees go on the output tray (max 12).
- Sign over the machine (`MachineEffects`, client only): title, recipe (3 logs → 1 tree), progress bar and status line. Yellow bar = logs toward the next tree, green = tree being made (server sets `CraftStart` / `CraftTime` attributes on the machine, not saved), red = tray full.
- Juice (`MachineEffects`): squish when logs go in, pop + sparkles when a tree comes out, chimney smoke, blinking light.

Next: [[Selling & Customers]]
