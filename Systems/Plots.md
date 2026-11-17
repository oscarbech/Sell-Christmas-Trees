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
One building along the road, then a back path, then the tree field. Full table in [[Butik & New Layout]].

| x | What |
|---|---|
| -156..-96 | [[Tree Lot]] + parking |
| -94..-86 | delivery drive |
| -84..-20 | butik (Christmas Store) |
| -20..20 | stand + lager (Tree Maker) |
| 20..36 | drive-in room |
| 36..58 | drive-in car lane ([[Drive-Thru]]) |

- Building z -17..35, back path z 37..45, field from z 51.5 (gate and middle path at x = 0). See [[Field & Expansions]].
- The road and the `Ground` part reach x -200 on the west side; cars spawn at x -196.

## Adding a plot
Copy `Plot1` and its `ServerStorage.PlotExpansions.Plot1` folder, move both by the same offset, and set `PlotIndex`. The full footprint is about 340 × 220 studs (x -200..138), so leave room for every expansion.

Related: [[Saving]], [[Shop Upgrades]]
