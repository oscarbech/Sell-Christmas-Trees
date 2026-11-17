---
tags: [design, planned]
---
# Butik & New Layout

Sketch from 2026-11-17. **Phase 1 (layout) is built**; phases 2-4 are planned. In game the butik is called the **Christmas Store**.

## Layout (road at the top, left → right)
**Tree lot** | **Butik** (new) | **Stand + lager** (the current tree shop, more space) | **Drive-thru** (stays)

- Road along the front.
- **Stand**: like now, part of the building; customers walk up to the counter. Give it more room.
- **Butik**: left section of the same building.
- **Lager**: the middle section behind the stand (Tree Maker); butik stock arrives here from the back path.
- **Path behind the building** for store deliveries (boxes for the butik), then the tree field at the bottom.

## Phase 1: what's built (2026-11-17, second try)
One building along the road, like the sketch. Offsets from the plot pivot (road at z -45, field behind at +z):

| x | Section | Unlocks with |
|---|---|---|
| -156..-96 | [[Tree Lot]] + parking | Expand Shop |
| -94..-86 | delivery drive (road to back path) | Delivery Path |
| -84..-20 | **Butik** (Christmas Store), front door x -58..-46 | Store Floor / Walls / Sign |
| -20..20 | **Stand + lager**: stand sticks out to z -23 at x -10..10; Tree Maker, tray, DEPOSIT / COLLECT / UPGRADE BACKPACK pads inside | Floor, Walls (first buttons) |
| 20..36 | **Drive-in** room: netting machine, NET TREES / TAKE NETTED, 2 pick-up windows in the east wall | Drive-Thru buttons |
| 36..58 | car lane: in next to the windows, U-turn at the back, out on the outer lane | Drive-Thru Lot |

- Building depth z -17..11. Doors: middle to butik and middle to drive-in at z 3..9, back door x -3..3 to the field.
- **Back path** (delivery lane) z 13..21 from x -94 to the car lane, with a yellow loading bay behind the lager. Built by Delivery Path.
- **Field** moved 14 studs back: the gate is at z 27.5. `FieldWalk` (x -3..3, z 11..27.5) goes from the back door across the back path to the gate.
- Shop floor for butik furniture: x -83..-21, z -16..10 (about 62 x 26).
- Nothing is there at the start: the middle comes first (Floor, Walls, then decorations), the drive-in chain starts after Walls, the lot after Leaderboard (Expand Shop), the butik after Expand Shop.
- The old buildings (big tree shop walls/floor, old drive-thru building + connector, shop wings, the first butik stock room) are kept in `ServerStorage.OldLayout_2026_11_17`, not deleted.

## Three ways to sell
| Where | How | Price |
|---|---|---|
| Stand | walk-up customers, first and easiest | one fixed tree price |
| [[Tree Lot]] | customers pick a tree themselves | **you set the tree price** (price board; higher = fewer buyers) |
| Butik | anything Christmas related, **no trees** | per item |

## Butik
1. Buy Christmas stock (ornaments, lights, wreaths, candles, stockings, gift wrap, snow globes, nutcrackers…); it arrives as boxes in the lager via the back path.
2. Buy furniture (shelves, tables, racks, gift table, register) and place it with a **grid placing system** (snap, rotate, move, sell back).
3. Stock furniture with the boxes; shoppers browse, pick items and pay; restock when empty. A Stocker worker later.

## Phases
1. ✅ Layout: one building (butik | stand + lager | drive-in), lot on the left, back path, field behind.
2. Grid placing system (server-checked, saved per plot).
3. Supplies, deliveries, stocking, butik shoppers.
4. Lot price board.

No rebirth in the game (removed 2026-11-17).
