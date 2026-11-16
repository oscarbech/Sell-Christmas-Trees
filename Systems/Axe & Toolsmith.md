---
tags: [system]
script: ReplicatedStorage.AxeOrbit, ServerScriptService.ToolsmithServer, StarterPlayerScripts.AxeSpinner
---
# Axe & Toolsmith

- The axe orbits every player inside the tree field. `AxeOrbit` holds the shared math; the server uses it to decide hits and clients draw the same orbit synced by server time.
- **Toolsmith:** opens after paying 750 on its pad; then you buy better axes from the TOOLSMITH menu. The axe level is saved on your own save.

| Axe | Price | Extra reach | Logs/tree |
|---|---|---|---|
| Wooden | 0 | 0 | 1 |
| Stone | 400 | 1.5 | 1 |
| Iron | 1,500 | 3 | 2 |
| Gold | 6,000 | 4.5 | 2 |
| Candy Cane | 25,000 | 6 | 3 |

Source: `TreeFarmConfig.Axes`. See [[Trees & Chopping]].
