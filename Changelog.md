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
