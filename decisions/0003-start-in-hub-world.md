# DDR-0003 - Start In Hub World

## Status

Accepted

## Decision

Shellbound will not use a traditional front-end menu as the main game entry.

After required Unity, studio, or startup screens, the game should load directly into:

```txt
_00_HubWorld
```

The player begins in The Great Shell hub world.

Settings and other menu-like functions should be available through in-world consoles in the hub. When the player is inside a world, the menu button can provide quick access to settings and practical pause functions.

## Reason

Shellbound should make the hub feel like the game itself, not a lobby before the game begins.

Starting directly in the hub supports:
- A more playful identity.
- Less separation between interface and world.
- A stronger sense that The Great Shell is home base.
- A different feel from standard game menu structures.

## Alternatives Considered

- Traditional main menu with New Game / Load Game / Options.
- Menu scene styled as the hub.
- Fully diegetic settings only, with no menu button access in worlds.

## Consequences

- `_00_HubWorld` needs to support first-load startup flow.
- Hub consoles need clear interaction language.
- Settings must still be accessible from worlds through the menu button.
- Save/load behavior needs to be designed carefully if there is no classic file-select screen.
- A beam-running loading screen can be added later, but is not required for the first prototype.
