---
tags: [design, planned]
---
# Butik & New Layout

Sketch from 2026-11-17. **Phase 1 (layout) is built**; phases 2-4 are planned. In game the butik is called the **Christmas Store**.

## Layout (road at the top, left → right)
**Tree lot** | **Butik** (new) | **Stand + lager** (the current tree shop, more space) | **Drive-thru** (stays)

- Road along the front.
- **Stand**: like now, part of the building; customers walk up to the counter. Give it more room.
- **Butik**: new building between the lot and the shop; the lot moves west to make room.
- **Lager**: storage room behind the stand, where butik stock arrives.
- **Path behind the building** for store deliveries (boxes for the butik), then the tree field at the bottom.

## Phase 1: what's built (2026-11-17)
- [[Tree Lot]] and its parking moved 66 studs west (x -180..-120); road and ground extended to x -200.
- Christmas Store shell at x -110..-54, z -23..22, built with 5 green BUILD buttons after Expand Shop (prices in [[Prices & Costs]]):
  - `BK_Floor`: floor, sidewalk in front, red carpet to the door.
  - `BK_Walls`: low white walls like the tree shop, front door (x -88..-76), east door to the shop link (z -12..-2), loading-door gap at the back (x -76..-64). No roof, so placing furniture is easy to see.
  - `BK_Sign`: CHRISTMAS STORE sign over the front door.
  - `BK_Lager`: stock room at the back (z 8..22): wall with doorway, concrete floor, 4 empty pallet racks, yellow roll-up loading door.
  - `BK_Delivery`: drive from the road (x -119..-111, DELIVERIES sign), lane behind the store (z 23..31) and a yellow loading dock at the back door.
- Shop floor for furniture: x -109..-55, z -22..8 (54 × 30).
- The stand is wider (see [[Selling & Customers]]).
- Pieces live in `EditStorage.RemovedForStart.Plot1.Plot` with `BuildId` `BK_*`; buttons are `Build_BK_*` ([[Edit Mode]]).

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
1. ✅ Layout: move the lot, butik shell (BUILD buttons), bigger stand, back path + lager door.
2. Grid placing system (server-checked, saved per plot).
3. Supplies, deliveries, stocking, butik shoppers.
4. Lot price board.

No rebirth in the game (removed 2026-11-17).
