# Technical Design

## Engine

Unity.

## Architecture

Early architecture should stay small and data-driven.

Early architecture should support:
- Third-person controller
- Camera system
- Collectibles
- Dialogue
- Shop
- Hub consoles
- Save data
- World completion state
- Hub state changes
- Direct boot into `_00_HubWorld`

## Dialogue Architecture

V1 dialogue should use three stable runtime boundaries:

- `DialogueTrigger` starts a named conversation from an NPC or interactable object.
- `DialogueController` owns start, advance, end, and player-control lockout.
- `DialogueStateStore` reads and writes named flags to the local JSON save.

Yarn Spinner is the default tool to evaluate. It should be adopted only if it supports custom UI, named nodes, variables or custom variable storage, commands/events, and local JSON persistence cleanly.

If Yarn is not acceptable, use a ScriptableObject fallback while keeping the same runtime boundaries.

## Scene Flow

Shellbound should not start at a traditional main menu.

Initial flow:
1. Show required Unity / studio / startup screens.
2. Load `_00_HubWorld`.
3. Put the player in The Great Shell hub.

The hub is the primary front door of the game.

World travel should happen from the hub through beam travel, world entrances, or other in-world devices.

Future loading transitions may use the turtle running on a beam, but that is not required for the current prototype.

## Save System

Save system needs to track:
- Restored beams
- Unlocked worlds
- Grunk amount
- Junk conversion state
- Purchased cosmetics
- Equipped cosmetics
- Hub decorations
- Collectibles
- Optional discoveries

First prototype save data should include named boolean flags for dialogue and simple progression checks.

Initial dialogue flags:

- `met_shellvis`
- `met_grunk`
- `heard_grunk_weirdness`
- `junk_converted_once`
- `cosmetic_purchased_once`

## Data Structure

Likely data-driven systems:
- Cosmetics
- Junk values
- Shop inventory
- Dialogue lines
- World completion data
- Collectible definitions

## Performance

Performance targets are not defined yet.

Early priorities:
- Stable movement feel
- Responsive camera
- Fast loading into test spaces
- Avoid overbuilding systems before the movement prototype is fun
