---
tags: [planning]
---
# Changelog

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
