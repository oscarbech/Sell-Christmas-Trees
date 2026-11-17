---
tags: [system]
script: ServerScriptService.Expansions
---
# Field & Expansions

Locked pieces live in `ServerStorage.PlotExpansions.<PlotName>` and are moved into the plot when bought. In Studio they sit in `Workspace.EditStorage.PlotExpansions` so you can see them ([[Edit Mode]]). `Expansions.apply(plot, fieldLevel, shopLevel, extras)` only changes what's different (no flashing, chopped trees stay chopped).

## Tree field
- **Starting field:** 6 columns × 3 rows of trees, with a path down the middle.
- **Expand Field:** 8 square chunks (`Field1`–`Field8`), 2 wide × 4 deep, 9 trees each, bought in order (row 1 west, row 1 east, row 2 west, …). Costs: see [[Prices & Costs]].
- West chunks carry the next piece of the **middle path**.
- 2026-11-17: the whole field moved 14 studs back (starting field z 29..55, front fence + gate at z 27.5) so the back path fits between the shop and the trees. Code: `Expansions` `FENCE_Z0` 55.5, `PATH_END_Z0` 55; `TreeFarmServer.gapPoints` z 8 (inside the back door) and 30.5 (through the gate).
- The **fence** around the field is built in code (`FieldFence`) from whichever chunks are open.
- The **Expand Field pad** sits at the far end of the path and moves forward as the path grows.
- Chunk trees come unlocked; there's no per-tree buying (see [[Trees & Chopping]]).
- The axe's field bounds (`FieldCFrame` / `FieldSize`) grow one row at a time.

## Other expansions
| Piece | Unlocked by |
|---|---|
| `ShopEast` / `ShopWest` | removed 2026-11-17 (archived in `ServerStorage.OldLayout_2026_11_17`); no room in the new building |
| ~~`Workshop`~~ | removed; its ground is the [[Drive-Thru]] now ([[Workshop & Decorating]]) |
| `TreeLot`, `LotDeco1..3` | OPEN TREE LOT, DECORATE LOT ([[Tree Lot]]) |
