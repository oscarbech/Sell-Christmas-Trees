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
- Lot (fence + floor) at x -114..-54, z -31..42; the arch faces the road at x -95..-73. That's 18 studs west of where it first was, leaving a gap from the tree shop like the [[Drive-Thru]] has on the east side.
- `LinkFloor` / `LinkWall` (Expand Shop build) bridge the gap from the shop's west wall to the lot.
- Parking ground in front of the lot (x -114..-54, z -44..-24). Parking spots at x -60, -68, -100, -108 (`SPOT_XS` in `ParkingLot`, must match the `Spot1..4` models).
- Presents can drop on the lot floor (`TycoonExtras`, area x -110..-58, z -18..10).
- The tree lot module finds its arch, stands and pads in the lot model itself, so moving the model is enough. Only `ParkingLot.SPOT_XS` and the `TycoonExtras` present area have positions written in code.
