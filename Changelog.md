---
tags: [planning]
---
# Changelog

## 2026-11-17
- Removed rebirth from the game: no rebirth pad, no +50% multiplier, no Rebirths on the leaderboard, not saved any more (`PlotManager`, `TreeFarmServer`). Tree price is now just 30 + 10 × shop level.
- Planned the new plot layout and the Butik (home-supplies shop with grid placing): [[Butik & New Layout]].
- Phase 1 of the new layout: [[Tree Lot]] + parking moved 66 studs west, road and ground extended to x -200, car spawn moved to x -196.
- New Christmas Store (butik) shell between the lot and the tree shop: floor, walls, sign, stock room, delivery path; 5 green BUILD buttons after Expand Shop ([[Prices & Costs]]).
- The stand is wider: booth, counter, sign, SELL TREES pad, wall gap and queue lane ([[Selling & Customers]]).
- Layout redone to match the sketch: **one building** along the road: butik (x -84..-20) | stand + lager with the Tree Maker (x -20..20) | drive-in room (x 20..36) with the car lane on its right. Tree lot on the far left (x -156..-96), back path behind the building, field moved 14 studs back with a walk from the back door to the gate ([[Butik & New Layout]]).
- Drive-thru moved into the building: lane, speaker, windows, netting machine; `DriveThru.CONFIG` lane numbers updated ([[Drive-Thru]]).
- Old big tree shop walls/floor, old drive-thru building + connector, shop wings and the first butik stock room archived in `ServerStorage.OldLayout_2026_11_17`.
- Shop wings gone, so the HIRE worker pads are not in the game for now ([[Workers]]).
- Whole shop building made 24 studs deeper (z -17..35): butik, stand + lager and drive-in share the new back wall; back path, field walk and field moved back to match; drive-in U-turn at z 32.
- Christmas Store opens: office PC (SANTA OS) to order stock and hire staff, delivery van + box pile in the lager, carry boxes to stock furniture, shoppers who buy and pay at the Checkout, Cashier and Stocker staff, Lumberjack / Tree Seller hired on the PC again ([[Store Stock & Staff]]). Checkout is now 2 x 2 with a clerk mat.
- Grid placing in the Christmas Store: BUILD MODE, 9 furniture pieces, snap-to-grid ghost, place / move / turn / sell, saved with the plot ([[Store Building]]).
- Roof on the whole building like the old drive-in: red upper walls + snowy red roof on the butik, the stand + lager and the drive-in, see-through while you're inside ([[Butik & New Layout]]).

## 2026-11-16
- Field expansion is now 8 square chunks (2 wide × 4 deep) instead of 7 strips; fence built in code ([[Field & Expansions]]).
- Middle path through the field; field gate moved onto it; Lumberjack uses the new gate.
- Chunk trees come unlocked, then per-tree buying turned off entirely (`TREES_COST_CASH = false`).
- Expand Field pad moved to the end of the path and follows it.
- `/wipe` command ([[Commands]]).
- Tree regrow: tried growing animations, kept the original bouncy pop + a green pulse when ready ([[Trees & Chopping]]).
- Chop debris now floats straight up out of the tree (anchored tween, no collision, max ~3 studs sideways) instead of flying off and bouncing around the field.
- Tree Maker sign above the machine: TREE MAKER, 3 logs → 1 tree, a progress bar (yellow logs 0-3/3, green making %, red tray full) and a status line ([[Tree Maker]]).
- New [[Drive-Thru]]: a standalone drive-thru shop ("Trees To Go") east of the tree shop. Cars order at a speaker, loop round the building and stop at a pick-up window; you hand out netted trees from inside. Built piece by piece with 10 purple BUILD buttons (lot, shop, sign, speaker, window, netting machine, then turbo, billboard, tip jar, second window). Replaces the old roadside LOAD CAR drive-thru.
- Netting machine inside the drive-thru shop: trees ride a conveyor through a funnel and come out wrapped in net. Only netted trees go on cars.
- Rebirth now also takes the drive-thru builds back down.
- Everything locked is now visible in Studio edit mode: BUILD button pieces, field chunks, shop wings, tree lot, workshop and car templates sit in `Workspace.EditStorage` and `EditStorageLoader` moves them into ServerStorage when the game starts ([[Edit Mode]]).
- Removed the Workshop (decorating) expansion. It also held the only rebirth pad, so rebirth has no pad for now ([[Workshop & Decorating]], [[Rebirth]]).
- [[Drive-Thru]] moved east onto the old Workshop ground and the building is now 40 × 40 (was 14 × 27): new walls with windows, bigger roof with 4 lamps, door on the west side with a path and crosswalk from the tree shop, bigger lot, lane and U-turn. Windows, netting machine, signs and the drive-thru BUILD buttons moved with it.
- Fixed the floating labels of the drive-thru and Expand Shop BUILD buttons: they hung over the road instead of above their buttons.
- [[Tree Lot]] moved 18 studs west (lot, decorations, parking, parking pad, Expand Shop button); the shop-to-lot link floor and wall stretched to match; parking spot positions and the present-drop area updated in code.
