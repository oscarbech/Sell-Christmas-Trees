---
tags: [system]
script: ServerScriptService.TycoonExtras, StarterGui.HUD.HUDController
---
# Daily Rewards & Quests

## Daily login reward
7-day streak, then it repeats. Reward = tree price × 5 / 8 / 12 / 16 / 20 / 30 / 50.

## Daily quests
| Quest | Goal | Reward |
|---|---|---|
| Chop trees | 25 | 150 |
| Sell trees | 10 | 150 |
| Earn cash | 500 | 350 |

Claimed quests are saved as `QuestClaimed_<Id>` on the plot. Source: `TreeFarmConfig.Quests` / `DailyRewards`.
