---
tags: [tech]
---
# Script Index

## ServerScriptService
| Script | Type | Purpose |
|---|---|---|
| `TreeFarmServer` | Script | main gameplay: chopping, deposit, collect, sell, pads, workers |
| `PlotManager` | Module | plots, economy config, saving, rebirth, wipe ([[Plots]], [[Saving]]) |
| `Expansions` | Module | field chunks, fence, shop wings, workshop, lot ([[Field & Expansions]]) |
| `CustomerQueue` | Module | shop customers ([[Selling & Customers]]) |
| `DriveThru` | Module | drive-thru shop: cars, orders, netting machine, pay ([[Drive-Thru]]) |
| `TycoonButtons` | Script | purple/green BUILD buttons, plot attribute `Built` |
| `ParkingLot` | Script | parking lot customers |
| `TreeLot` | Module | [[Tree Lot]] |
| `TreeUnlocks` | Script | per-tree buying, turned off ([[Trees & Chopping]]) |
| `ToolsmithServer` | Script | [[Axe & Toolsmith]] |
| `TycoonExtras` | Script | [[Events]], [[Offline Earnings & Presents]], daily reward, leaderboard |
| `PlayTogetherServer` | Script | [[Play Together]] |
| `CheatCommands` | Script | [[Commands]] |

## ReplicatedStorage
| Module | Purpose |
|---|---|
| `TreeFarmConfig` | icons, axes, events, daily rewards, quests, Robux shop |
| `AxeOrbit` | shared axe orbit math |
| `NettedTree` (model) | the netted tree the drive-thru machine makes |

## StarterPlayerScripts
`AxeSpinner`, `TreeEffects`, `MachineEffects`, `SellEffects`, `CameraShake`, `EventBanner`, `BuildEffects`, `BuildPreview`, `CarryAnimation`, `DriveThruEffects` (netting machine juice, shop roof fade: [[Drive-Thru]])

## StarterGui.HUD
`HUDController` (stats, tutorial, Robux shop, quests), `PlayTogetherController`, `ToolsmithController`, `SettingsController`

## ServerStorage
- `RemovedForStart.<Plot>.Plot`: pieces the BUILD buttons drop in (drive-thru pieces are `DT_*`).
- `OldScripts.DriveThru_v1_roadside`: the old roadside drive-thru module, kept as a backup.
