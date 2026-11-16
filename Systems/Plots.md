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
- Shop in front, tree field behind it, street along the front.
- Field gate and middle path at the centre line (x = 0). See [[Field & Expansions]].
- Expansions: tree lot on the west, workshop on the east ([[Tree Lot]], [[Workshop & Decorating]]).

## Adding a plot
Copy `Plot1` and its `ServerStorage.PlotExpansions.Plot1` folder, move both by the same offset, and set `PlotIndex`. The full footprint is about 260 × 220 studs, so leave room for every expansion.

Related: [[Saving]], [[Shop Upgrades]]
