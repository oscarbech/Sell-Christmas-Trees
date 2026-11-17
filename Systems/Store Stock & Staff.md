---
tags: [system]
script: ServerScriptService.StoreShop, StarterPlayerScripts.StoreComputerController, ReplicatedStorage.StoreProducts
---
# Store Stock & Staff (office PC)

Phase 3 of [[Butik & New Layout]]. The Christmas Store sells Christmas stuff (no trees) that you order on an office PC, put on your furniture ([[Store Building]]) and sell to shoppers.

## Office PC ("SANTA OS")
- BUILD button **Office PC** (`BK_PC`, 750, after Delivery Path): a desk with a monitor in the lager (middle section, east side, x 12..18, z 13..20).
- Walk up and press **E** ("Use computer"). Only the plot owner. Walking away closes it.
- Apps:
  - **Stock**: order boxes (ORDER = 1 box, x5 = 5 boxes). Shows boxes in the lager, the van status.
  - **Staff**: hire, upgrade, fire.
  - **Store**: OPEN / CLOSED (and why), items on display, boxes, shoppers, items sold, store earnings.

## Stock
| Product | Box of | Box cost | Sells each | Profit / box |
|---|---|---|---|---|
| Ornaments | 12 | 60 | 12 | 84 |
| Candles | 10 | 60 | 14 | 80 |
| Fairy Lights | 8 | 80 | 22 | 96 |
| Gift Wrap | 8 | 80 | 20 | 80 |
| Stockings | 6 | 90 | 30 | 90 |
| Wreaths | 6 | 120 | 40 | 120 |
| Snow Globes | 5 | 150 | 60 | 150 |
| Nutcrackers | 4 | 200 | 90 | 160 |

- The lager holds 24 boxes (incl. ones on the way).
- **Delivery**: a red van drives in from the west end of the road, down the delivery drive and along the back path to the loading bay (x -11, z 41). It waits 2 s so quick orders ride together. The boxes fly over the back wall onto the **box pile** in the lager (x -17..-11, z 13..22, 3 x 4 spots, 2 high), then the van drives back out.
- **Pick up** a box: walk to it and press **E** ("Pick up"). You can't carry a box and trees at once. **DROP BOX** (button, bottom right) puts it back on the pile.
- **Stocking**: walk past display furniture with the box and the items hop onto it (within 7 studs). Each piece holds **one product** (up to its Slots); empty it to change product. When the box is empty it disappears.

## Shoppers
- The store is **OPEN** when its walls are built, there's at least one **Checkout** and something is on display.
- Shoppers (your friends' avatars, or a few default ones) walk in from the sidewalk at the front door, carry a red basket, pick 1-3 items from stocked furniture (pathfinding around your layout), then queue at the Checkout with the shortest line.
- **Ringing up**: stand on the yellow clerk mat behind a Checkout (0.8 s per shopper), or hire a Cashier. They pay the items' sell price (cash popup at the checkout).
- A shopper who waits 50 s gives up and puts the items back.
- One every 11 s, minus 0.8 s per decor piece (Rug, Decor Tree, Candy Lamp), at least 3.5 s. Up to 3 + 2 per Checkout shoppers at once (max 8).

## Staff (hired on the PC)
| Job | Hire / upgrades | What they do |
|---|---|---|
| Cashier | 1,500 / 4,000 / 9,000 | stands at the first Checkout and rings up (1.6 s / 1.1 s / 0.7 s) |
| Stocker | 3,000 / 7,000 / 15,000 | takes boxes off the pile and fills furniture that needs them (walk speed 10 / 13 / 16) |
| Lumberjack | 500 | the old field worker ([[Workers]]) |
| Tree Seller | 2,500 | the old stand worker ([[Workers]]) |

FIRE sets the job back to 0 (no refund).

## Tech
- `ReplicatedStorage.StoreProducts`: products, item + box models, parse/serialize.
- Plot attributes (saved by PlotManager, [[Saving]]): `StoreBoxes` = `bid:product:units;...` (pile), `StoreStock` = `furnitureUid:product:count;...`, numbers `StaffCashier`, `StaffStocker`, `StoreSold`, `StoreEarned`, `StoreBoxNext`. Live only: `StorePending`, `StoreVanLoad`, `StoreVanETA`, `StoreOpen`, `StoreClosedWhy`, `StoreShoppers`. Player attribute `CarryBox` while carrying.
- Remotes in `ReplicatedStorage.Store`: `Order(product, count)`, `Hire(job)`, `FireStaff(job)`, `DropBox()`.
- Plot folders: `StoreBoxPile`, `StoreVans`, `StoreShoppers`, `StoreStaff`; furniture pieces get a `Stock` folder with the item models on their `Slot` attachments.
- Checkout: `PayPoint` (front, where shoppers queue) and `RegisterPoint` (yellow mat behind it). It's 2 x 2 cells now.
- NPCs: anchored HumanoidRootPart tweened along PathfindingService waypoints.
- Carried boxes and trees are blocked from mixing (`TreeFarmServer` collect check, `StoreShop` pick-up check).
