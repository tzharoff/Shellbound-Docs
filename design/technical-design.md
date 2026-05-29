# Technical Design

## Engine

Unity.

## Architecture

Not defined yet.

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
