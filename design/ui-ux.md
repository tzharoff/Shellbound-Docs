# UI / UX

## HUD

Not defined yet.

Likely HUD elements:
- Health or hit state
- Junk / Grunk readout
- Interaction prompts
- Contextual collectible feedback

## Dialogue UI

Dialogue uses a 2D overlay with:
- Portrait
- Character name
- Dialogue text
- Continue prompt

Portraits use simple low-frame animation.

## Inventory

Inventory should be simple and readable.

Possible categories:
- Junk
- Cosmetics
- Bobbleheads
- Key items
- World oddities

## Shop UI

Shellvis shop should sell cosmetics and hub decorations for Grunk.

Important UI needs:
- Preview cosmetics when possible.
- Clearly show Grunk cost.
- Support funny descriptions.
- Never imply stat upgrades.

## Menu Philosophy

Shellbound should not use a traditional front-end menu as the primary game entry.

After load screens, the game should load directly into `_00_HubWorld`.

Menu-like functions should exist inside the world whenever possible.

## Hub Consoles

The hub contains consoles the player can walk up to and use.

Console candidates:
- Settings
- Accessibility
- Display / audio
- Save or file management if needed
- Collection review
- World progress
- Credits or studio information if needed

The point is to make configuration feel like part of the place, not a separate product shell.

## World Menu Button

In worlds, the menu button can open quick access to the same settings functions.

This should be practical first:
- Resume
- Settings
- Accessibility
- Controls
- Return to hub if supported

The world-access version can be more conventional than the hub consoles, but it should still feel visually connected to Shellbound.

## Loading Screens

Expected load flow:
1. Unity / studio / required startup screens.
2. Load into `_00_HubWorld`.
3. Use beam travel or world entry points from the hub.

Future loading screen idea:
- The turtle running on a beam.

For now, loading can stay simple.

## Accessibility

Accessibility is not defined yet.

Starter considerations:
- Subtitle support
- Remappable controls
- Camera sensitivity
- Reduced flashing / effects options
- Clear collectible and interaction feedback
