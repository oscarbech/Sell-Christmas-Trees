---
tags: [system]
script: ServerScriptService.PlotManager
---
# Plots

Every player gets their own plot (tycoon) when they join. Plots live in `Workspace.Plots` (`Plot1`, …), sorted by the `PlotIndex` attribute.

- Economy values are **attributes on the plot model**: `Cash`, `BackpackLevel`, `FieldLevel`, `ShopLevel`, worker levels, `Total*` stats, `QuestClaimed_*`.
- What you carry is on the **player**: `Logs`, `Trees`, `MaxLogs`.
- `player:GetAttribute("Plot")` = the plot the player is playing on (can be a friend's, see [[Play Together]]).
- If every plot is taken, the player visits a random plot.
- The shop sign shows `<Name>'s Shop`.

## Layout (relative to plot pivot)
Road along the front, buildings in a row, tree field behind (see [[Butik & New Layout]]):

| x | What |
|---|---|
| -180..-120 | [[Tree Lot]] + parking |
| -119..-111 | store delivery drive |
| -110..-54 | Christmas Store (butik) + stock room |
| -54..-29 | shop link / west wing (Expand Shop) |
| -31..30 | tree shop with the stand at the front (x -10..10) |
| 47..108 | [[Drive-Thru]] |

- Field gate and middle path at the centre line (x = 0). See [[Field & Expansions]].
- Behind the store: the delivery lane (z 23..31, x -119..-32).
- The road and the `Ground` part reach x -200 on the west side.

## Adding a plot
Copy `Plot1` and its `ServerStorage.PlotExpansions.Plot1` folder, move both by the same offset, and set `PlotIndex`. The full footprint is about 340 × 220 studs (x -200..138), so leave room for every expansion.

Related: [[Saving]], [[Shop Upgrades]]
