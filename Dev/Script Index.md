---
tags: [tech]
---
# Script Index

## ServerScriptService
| Script | Type | Purpose |
|---|---|---|
| `TreeFarmServer` | Script | main gameplay: chopping, deposit, collect, sell, pads, workers |
| `PlotManager` | Module | plots, economy config, saving, wipe ([[Plots]], [[Saving]]) |
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
| `StoreShop` | Script | Christmas Store stock, delivery van, box pile, stocking, shoppers, Cashier / Stocker, PC remotes ([[Store Stock & Staff]]) |
| `StoreServer` | Script | Christmas Store furniture: place / move / sell, builds the pieces ([[Store Building]]) |
| `EditStorageLoader` | Script | moves `Workspace.EditStorage` into ServerStorage at start ([[Edit Mode]]) |

## ReplicatedStorage
| Module | Purpose |
|---|---|
| `TreeFarmConfig` | icons, axes, events, daily rewards, quests, Robux shop |
| `AxeOrbit` | shared axe orbit math |
| `StoreFurniture` | store furniture catalog, grid and models ([[Store Building]]) |
| `StoreProducts` | store stock: products, item + box models ([[Store Stock & Staff]]) |
| `NettedTree` (model) | the netted tree the drive-thru machine makes |

## StarterPlayerScripts
`AxeSpinner`, `TreeEffects`, `MachineEffects`, `SellEffects`, `CameraShake`, `EventBanner`, `BuildEffects`, `BuildPreview`, `CarryAnimation`, `DriveThruEffects` (netting machine juice, shop roof fade: [[Drive-Thru]]), `StoreBuildController` (store build mode: [[Store Building]]), `StoreComputerController` (office PC + DROP BOX: [[Store Stock & Staff]])

## StarterGui.HUD
`HUDController` (stats, tutorial, Robux shop, quests), `PlayTogetherController`, `ToolsmithController`, `SettingsController`

## ServerStorage
In Studio, `RemovedForStart`, `PlotExpansions` and `Cars` sit in `Workspace.EditStorage` and are moved here when the game starts ([[Edit Mode]]).
- `RemovedForStart.<Plot>.Plot`: pieces the BUILD buttons drop in (drive-thru pieces are `DT_*`).
- `OldScripts.DriveThru_v1_roadside`: the old roadside drive-thru module, kept as a backup.
