---
tags: [system]
script: ServerScriptService.TreeLot
---
# Tree Lot

- OPEN TREE LOT (2,500, needs Shop level 1) adds a display yard west of the shop.
- Carry trees to STOCK DISPLAY and they hop onto empty stands.
- Shoppers walk in through the arch, look at a tree and often buy it for **tree price × 1.5** (more with decorations and decorated trees).
- MORE STANDS: 4 → 8 → 12 stands.
- DECORATE LOT: lamps, reindeer, giant tree. More shoppers, who buy more and pay more.
- Stock on display is saved ([[Saving]]).

## Layout (offsets from the plot pivot)
- Lot (fence + floor) at x -180..-120; the arch faces the road at x -161..-139. Moved 66 studs west on 2026-11-17 to make room for the [[Butik & New Layout|Christmas Store]] between the lot and the tree shop. The store's delivery drive (x -119..-111) runs between the store and the lot.
- `LinkFloor` / `LinkWall` (Expand Shop build) bridge the gap from the shop's west wall to the Christmas Store (x -54..-29).
- Parking ground in front of the lot (x -180..-120, z -44..-24). Parking spots at x -126, -134, -166, -174 (`SPOT_XS` in `ParkingLot`, must match the `Spot1..4` models). Cars come in from the west end of the road at x -196 (`SpawnX` in `ParkingLot` and `DriveThru`).
- Presents can drop on the lot floor (`TycoonExtras`, area x -176..-124, z -18..10).
- The tree lot module finds its arch, stands and pads in the lot model itself, so moving the model is enough. Only `ParkingLot.SPOT_XS` and the `TycoonExtras` present area have positions written in code.
