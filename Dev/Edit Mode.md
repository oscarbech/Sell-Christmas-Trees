---
tags: [tech]
script: ServerScriptService.EditStorageLoader
---
# Edit Mode

Everything that is locked at the start of the game is visible in Studio edit mode, in the spot where it appears when bought. You can see it and edit it in place.

It all sits in `Workspace.EditStorage`:

| Folder | Moved to at game start | Used by |
|---|---|---|
| `RemovedForStart.<Plot>` | `ServerStorage.RemovedForStart` | BUILD button pieces, drive-thru, parking, old pads ([[Drive-Thru]], `TycoonButtons`, `ParkingLot`) |
| `PlotExpansions.<Plot>` | `ServerStorage.PlotExpansions` | field chunks, shop wings, tree lot, workshop ([[Field & Expansions]]) |
| `Cars` | `ServerStorage.Cars` | car templates, parked on the street (`DriveThru`, `ParkingLot`) |
| `EditOnly.<Plot>.FieldFence` | deleted | preview of the full field fence. The real one is built in code from the open chunks |

`EditStorageLoader` (server script) moves each folder into ServerStorage in one go when the game starts. The other scripts `WaitForChild` those folders, so they only start once the move is done. Nothing in ServerStorage needs editing by hand any more.

## Things to know
- Because everything shows at once, some pieces overlap in edit mode:
  - the shop wings (`ShopEast` / `ShopWest`) and the walls they replace;
  - the old Shop East wing / Workshop and the drive-thru;
  - the starting field's back fence and the first field chunks.
  In the game only one of each is ever out.
- New locked pieces go in `EditStorage` (under the right folder, with their `BuildId`), not in ServerStorage.
- Adding a plot: copy `Plot1` and its folders under `EditStorage.RemovedForStart` and `EditStorage.PlotExpansions`, and move them all by the same offset ([[Plots]]).
- Still runtime-only (they move or are made per player): customers, workers, cars on the road, presents, chopped logs, effects. Small templates in ReplicatedStorage (`NettedTree`, `MiniTree`, `DecoratedTree`, `SpinAxe`) also stay there.
