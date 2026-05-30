# Devlog 0007 - HUD and Dialogue Pause

## Date

2026-05-30

## Summary

We built the HUD and fixed a problem where enemies could hit the player during dialogue.

The HUD shows the player's lives and Grunk balance. It also shows a prompt when the player is near something they can interact with. When a dialogue box is open, the game world freezes so nothing can hurt the player while they are reading.

## What We Built

### The HUD

The HUD has three elements.

**Lives. Top-left.**

Shows how many lives the player has. Updates automatically when a life is lost or restored.

**Grunk balance. Top-right.**

Shows the current Grunk total. When the number changes, the display does a small scale pulse so the player notices it even if they are not looking at the corner of the screen.

**Interaction prompt. Bottom-center.**

A small text prompt that fades in when the player is near anything they can interact with. Fades out when they move away or when a dialogue box opens.

The prompt does not pop on or off. It fades smoothly so it does not distract when the player is just passing by.

An editor tool builds the entire HUD canvas automatically. One menu item, everything wired.

### Dialogue Pauses the World

When a dialogue box opens, the game sets the time scale to zero.

Time scale zero means nothing moves. Physics stops. Enemy AI stops. Particles and animations freeze. The player cannot be chased, pushed, or hit while reading a line of text.

When the dialogue box closes, time scale goes back to one and everything resumes.

The typewriter effect inside the dialogue box uses real-time instead of game time. This means the letters keep appearing at normal speed even while the world is frozen.

## Key Decisions

**Pause the whole world during dialogue, not just the player.**

Locking player movement was not enough. If enemies were still active, they could close the distance or attack during a conversation. Setting time scale to zero is the simplest and most complete solution.

**Use real-time for the typewriter.**

The typewriter runs on wall-clock time so it is not affected by the pause. Text appears normally. The player can still skip to the end and advance through lines. Nothing feels stuck.

**The interaction prompt fades, it does not pop.**

A hard on-off prompt is visually noisy. A short fade makes the prompt feel like part of the world rather than an alert.

**The prompt hides during dialogue.**

Once a conversation is open, showing the interact prompt would be confusing. It disappears when dialogue is running and returns when the conversation ends.

**HUD is minimal.**

Lives and Grunk are the only things on screen. No health bar. No stamina bar. No objective tracker. The game should feel open and exploratory, not loaded with information.

More elements can be added later if they are needed. Nothing goes on the HUD without a clear reason.

## Open Questions

- Will the HUD need a Grunk icon or symbol, or is the letter G enough?
- Should the interaction prompt label change based on context? For example, Save vs Talk vs Inspect?
- What happens to the HUD during a boss fight intro?

## Next Session Goal

Build the shop system so Shellvis can sell cosmetics to the player and the Grunk economy becomes a real loop.
