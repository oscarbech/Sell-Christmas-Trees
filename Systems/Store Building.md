---
tags: [system]
script: ServerScriptService.StoreServer, StarterPlayerScripts.StoreBuildController, ReplicatedStorage.StoreFurniture
---
# Store Building (grid placing)

Phase 2 of [[Butik & New Layout]]. The plot owner furnishes the Christmas Store (butik) with a grid build mode.

## How it plays
- Stand inside your store (its walls built, `BK_Walls`) and a green **BUILD MODE** button shows at the bottom.
- Build mode shows a catalog bar (3D preview + price) and grid lines on the floor. Red cells (inside the front door, and in front of the door to the stand + lager) must stay free.
- Pick a piece: a ghost follows the mouse, snapped to 4-stud cells. Green = fits, red = doesn't (or you can't afford it).
  - **Click** to place (you keep placing the same piece), **R** to turn, **Q** / Esc to cancel.
  - Mobile: tap the floor to aim, then **PLACE** / **TURN** / **CANCEL**.
- Click (tap) a placed piece: **MOVE** (free), **TURN** (free), **SELL** (half the price back).
- Placed pieces pop in; the server shows the usual cash popup.
- Build mode closes when you walk out of the store.

## Catalog
| Piece | Price | Cells | Holds | Kind |
|---|---|---|---|---|
| Wall Shelf | 150 | 2 x 1 | 6 | display |
| Ornament Rack | 120 | 1 x 1 | 4 | display |
| Candle Stand | 100 | 1 x 1 | 3 | display |
| Display Table | 250 | 2 x 2 | 8 | display |
| Gift Table | 500 | 3 x 2 | 12 | display |
| Checkout | 400 | 2 x 2 | - | register (shoppers pay here; clerk mat behind it) |
| Holiday Rug | 80 | 2 x 3 | - | decor |
| Decor Tree | 150 | 1 x 1 | - | decor |
| Candy Lamp | 60 | 1 x 1 | - | decor (light) |

Max 60 pieces per store. Prices are placeholders until the store sells stock.

## Tech
- `ReplicatedStorage.StoreFurniture`: catalog, grid, models (built in code, shared by server and client), `check` (bounds, doorway cells, overlaps), `parse` / `serialize`.
- Grid: cell (0,0) corner at x -82.5, z -15.5 from the plot pivot, 15 x 12 cells of 4 studs (covers x -82.5..-22.5, z -15.5..32.5). Floor height `FLOOR_Y` 0.2.
- Saved as the plot attribute `Furniture` = `uid:id:gx:gz:r;...` (r = quarter turns). PlotManager saves / loads it and `/wipe` clears it ([[Saving]]).
- `StoreServer` builds the pieces into `Plot.StoreFurniture` from the attribute (only while `BK_Floor` is built). Remotes in `ReplicatedStorage.Store`: `Place(id, gx, gz, r)`, `Move(uid, gx, gz, r)`, `Sell(uid)`, each returns `(ok, message)`. Only the plot owner, only with `BK_Walls` built.
- Display pieces carry `Slot` attachments (where stock sits), the Checkout has `PayPoint` (queue) and `RegisterPoint` (clerk mat). Stock, shoppers and staff: [[Store Stock & Staff]].
- `StoreBuildController` (client): UI, ghost, grid lines, input. Store area check x -84..-20, z -18..35.
