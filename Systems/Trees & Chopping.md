---
tags: [system]
script: ServerScriptService.TreeFarmServer, StarterPlayerScripts.TreeEffects, ServerScriptService.TreeUnlocks
---
# Trees & Chopping

- Each tree is a model with a `Stump` and a `Top` (5 leaf layers + tip), with a `TreeId` attribute (`B1..`, `F<chunk>_<n>`).
- The axe orbits you in the field and chops trees in range ([[Axe & Toolsmith]]). Logs per tree depend on the axe; Lumber Frenzy doubles it ([[Events]]).
- The server only flips `Ready` (+ `HitBy` / `HitPoint`); all visuals are client-side in `TreeEffects`.
- **Regrow:** 45 s (`RegrowTime`). The tree disappears, then comes back with a bouncy pop and a short green pulse.
- **Backpack full:** trees in reach pulse red and do a little "nope" shake.
- **Golden trees:** pay tree price × 8 straight to cash; Golden Hour spawns more ([[Events]]).

## Tree unlocking (turned off)
`TreeUnlocks` used to make players buy each tree. It's switched off with `TREES_COST_CASH = false`, so every tree is free. Set it to `true` to bring it back.
