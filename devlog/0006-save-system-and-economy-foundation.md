# Devlog 0006 - Save System and Economy Foundation

## Date

2026-05-30

## Summary

We built the save system and the Grunk economy foundation.

The game can now remember everything important across sessions. Grunk can be earned, spent, and saved. The player can choose from three save slots. Preferences like volume and sensitivity are stored separately and survive a new game.

## What We Built

### The Save System

One file per slot. Three slots total.

Each file is named save_0.json, save_1.json, or save_2.json. The game reads and writes to whichever slot is active.

Each save file tracks:

- Grunk balance.
- Dialogue flags that have been set.
- Which cosmetic is equipped.
- Which cosmetics have been purchased.
- Which beams have been restored.
- Which worlds have been unlocked.
- Which collectibles have been picked up.
- When the file was last saved.

### Preferences

A separate file called preferences.json stores settings that should never be wiped.

Volume, sensitivity, display settings. A new game clears the save slot but leaves preferences alone.

### Save Points

Save points are physical objects placed in world scenes. The player walks up to one and presses the interact button. The game saves and plays a small feedback effect.

Scene transitions also auto-save. Every time the player moves between scenes, the game writes to the active slot automatically. The player should never lose progress because they forgot to save.

### Grunk

Grunk is the currency of Shellbound. It is also the name of the NPC who converts junk into Grunk.

The GrunkManager handles add, spend, and balance checks. When the balance changes, it fires an event. The HUD listens to that event and updates the display.

Collectibles in the world award Grunk when picked up. Each collectible has a stable ID. Once picked up, it is recorded in the save file and will not reappear after a scene reload.

### IInteractable

We added a small interface called IInteractable. Any object the player can press the interact button on implements this interface.

Right now that includes:

- DialogueTrigger. Starts a conversation.
- SavePoint. Saves the game.

Future objects like shop triggers, hub consoles, and signs will implement the same interface. The player controller does not need to change when new interactable types are added.

## Key Decisions

**Three save slots.**

The player can have up to three separate saves. Each one is completely independent.

**New game wipes the slot. Preferences survive.**

Starting a new game clears the selected slot's file. Volume settings and other preferences are untouched.

**Save on physical save points and on scene transitions.**

The player can choose when to save by using a save point. The game also saves automatically during scene transitions as a safety net.

**Collectibles do not respawn.**

Once a collectible is picked up, it is gone for that slot. This avoids situations where the player farms the same item over and over. The save file remembers which ones are gone.

**Monsters respawn. Collectibles do not.**

Going back to a world means enemies are back and the fight is possible again. Junk and collectibles are already gone.

**Boss fights will be replayable from the hub.**

The first time the player beats a boss, the beam is restored. That is permanent.

After that, a challenge portal appears in the hub. The player can use it to fight the boss again. The re-fight is optional and does not restore anything. The beam stays restored regardless of the outcome.

This keeps boss fights available for fun without creating save state conflicts.

**Beams are one-way.**

Once a beam is restored it stays restored. There is no way to un-restore one.

**Collectible IDs are world-scoped.**

A collectible in Sunny Shore is named something like sunnyshore_junk_01. This keeps IDs from colliding if two worlds have similar items.

## Open Questions

- What does the slot select screen look like?
- Does the hub have a save point, or does returning to the hub auto-save?
- What is the maximum Grunk amount the player can hold?

## Next Session Goal

Build the HUD so the player can see their Grunk balance and know when they can interact with something.
