---
tags: [system]
script: ServerScriptService.DriveThru, StarterPlayerScripts.DriveThruEffects, ServerScriptService.TycoonButtons
---
# Drive-Thru

A standalone drive-thru shop ("Trees To Go"), like a McDonald's: its own small building east of the tree shop, just south of the road, with a lane looping round it. Cars turn off the road, order at the speaker, drive round the back and stop at the pick-up window. You hand them **netted trees** through the window.

It is separate from the tree shop (own building, own door, a path and crosswalk from the tree shop's open south side), but the trees still come from the [[Tree Maker]] tray and are carried the normal way.

## How it plays
1. COLLECT TREES at the Tree Maker as usual.
2. Walk the path to the drive-thru shop and in through the west door. Stand on **NET TREES**: the tree goes into the netting machine (holds 6).
3. The machine pulls the tree through the funnel and it comes out wrapped in white net, trunk sticking out (3 s per tree). Netted trees wait on the rack (holds 6).
4. **TAKE NETTED** picks them up (as many as you can carry).
5. Stand on the green **HAND OUT** tile at a pick-up window while a car is there (or stand right beside the car outside): the tree flies onto the roof, gets strapped down, and you're paid for that tree. When the order is full the car drives back onto the road.

- Cars order 1–2 trees (big cars sometimes 3). The order shows in a bubble over the car from the speaker onward (`0/2 NETTED TREE`).
- Only netted trees go on a car. A plain tree in your arms does nothing at the window.
- Netted trees can still be sold to walk-up customers at the normal price, so you're never stuck holding one.
- Pay per tree: **tree price × 2** (× 1.5 more with the tip jar), and the sell combo counts. See [[Prices & Costs]].
- Car Parade event: cars come 3× as often ([[Events]]).
- While you're inside, the roof and upper walls fade so you can see yourself work.

## Buying it (tycoon buttons)
Built piece by piece with the purple BUILD buttons, one after another. Each piece drops in when bought. The first button appears once the tree shop's Walls are built.

| # | Button | Price | What appears / does |
|---|---|---|---|
| 1 | Drive-Thru Lot | 500 | asphalt lot, the lane, foundation, path from the tree shop |
| 2 | Drive-Thru Shop | 600 | the building: walls, windows, roof |
| 3 | Shop Sign | 300 | TREES TO GO roof sign, roadside pole sign |
| 4 | Order Speaker | 400 | menu board + speaker on the entry lane |
| 5 | Pick-Up Window | 500 | window 1 (counter, awning). **Cars start coming.** |
| 6 | Netting Machine | 700 | the machine, rack and the two pads inside. Now you can serve. |
| 7 | Turbo Netter | 2,500 | extra motor: netting takes 1.5 s instead of 3 s |
| 8 | Billboard: More Cars | 4,000 | tall roadside billboard: a car every 8 s instead of 14 s, up to 5 cars on the lot instead of 3 |
| 9 | Tip Jar: +50% Pay | 6,000 | tip jar by the windows: every drive-thru tree pays × 1.5 |
| 10 | Second Window | 8,000 | pick-up window 2 opens (shutter goes up): two cars are served at once |

Until the Netting Machine is built, cars at the window show `BUILD THE NETTING MACHINE`.

## Saving and rebirth
- What's built is the plot's `Built` list (ids `DT_Lot`, `DT_Shop`, `DT_Sign`, `DT_Speaker`, `DT_Window`, `DT_Netter`, `DT_Turbo`, `DT_Billboard`, `DT_Tips`, `DT_Window2`), saved by PlotManager like the other BUILD buttons ([[Saving]]).
- A [[Rebirth]] takes the drive-thru back down (every `DT_` id is dropped from `Built`); the tree shop's own builds stay.
- Trees inside the netting machine or on its rack are not saved.

## Tech notes
- Pieces wait in `ServerStorage.RemovedForStart.<Plot>.Plot` with a `BuildId` attribute (in Studio: `Workspace.EditStorage.RemovedForStart`, see [[Edit Mode]]); buttons are `Build_DT_*` in the plot's `BuildButtons`. Prices and order are attributes on the buttons (`Price`, `Requires`).
- `DriveThru` (server): cars, the lane path, orders, the netting machine, pay. Numbers are in its `CONFIG`. Positions are offsets from the plot pivot, so a copied plot works.
- `DriveThruEffects` (client): machine sign + progress bar, conveyor, the tree riding through the funnel, sparkles, turbo fan, roof fade.
- `ReplicatedStorage.NettedTree`: the netted tree model (attribute `Netted`).
- `TreeFarmServer` calls `DriveThru.canFeed/feed`, `canTake/take`, `carNear`, `load`.
- The old `DriveThruLevel` number is kept in step (1 when cars can come) because the Car Parade event and the Car Loader use it. The old roadside version of the script is kept in `ServerStorage.OldScripts.DriveThru_v1_roadside`.
- The old DRIVE-THRU / LOAD CAR pads are no longer used (they sit in `RemovedForStart.<Plot>.Pads`).

## Open points
- The old Shop East wing and Workshop expansions (not reachable right now) would stand on the same ground as the drive-thru if they're brought back.
- The [[Workers|Car Loader]] isn't hooked up to the new shop (his pad is not in the game right now). If he's brought back, trees he loads get netted automatically.
- "Second lane" became a second pick-up window on the same lane: there's no room for a second lane that still passes the building.
