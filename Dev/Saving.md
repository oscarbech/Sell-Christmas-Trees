---
tags: [tech]
script: ServerScriptService.PlotManager
---
# Saving

- DataStore: **`ChristmasTreeTycoon_v1`**, key `u_<UserId>`.
- Saved on leave, every 90 s (autosave) and on shutdown (`BindToClose`).
- If a save can't be loaded, `canSave` stays false so it's never overwritten.
- Saved: every number in `SAVED_NUMBERS` (cash, levels, workers, daily streak, totals), quests, machine/decorator contents, tree lot stock, axe level, [[Settings]].
- Guests' earnings go to the host's save ([[Play Together]]).

To reset your own save while testing: `/wipe` ([[Commands]]).
