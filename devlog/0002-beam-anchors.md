# Devlog 0002 - Beam Anchors

## Date

2026-06-01

## Summary

Defined Beam Anchors as Shellbound's checkpoint and respawn system.

This replaced the idea of traditional lives with a softer world-based respawn structure that better supports exploration and curiosity.

## Accomplished

- Decided the player uses 3 Hearts.
- Decided Shellbound will not use traditional lives for the current design direction.
- Decided death should not remove Grunk.
- Defined Beam Anchors as world checkpoints.
- Defined Beam Anchors as large ancient anchor-shaped structures.
- Connected Beam Anchors to the beam network fiction.
- Added Anchor Polish as an item sold by Shellvis.
- Added the "Clean All The Anchors" achievement concept.
- Added the Old Sailor's Hat cosmetic reward.

## Key Decisions

- Beam Anchors are the respawn points inside each world.
- Player respawns at the most recently activated Beam Anchor.
- Hearts are restored on respawn.
- The player is not sent back to the hub after losing all hearts.
- Anchor restoration should support world completion.
- Anchor restoration should unlock expression-based rewards, not power.

## Design Notes

The anchor idea works because Shellbound is about reconnecting worlds that have drifted apart.

Anchors prevent things from drifting.

This turns checkpoints into part of the fiction instead of abstract game objects.

Shellvis selling Anchor Polish gives Grunk another use and connects the economy to world restoration.

## Example Reward

Achievement:

```txt
Clean All The Anchors
```

Requirement:

```txt
Restore every Beam Anchor.
```

Reward:

```txt
Old Sailor's Hat
```

## Next Session Goal

Define the first playable prototype version of the Beam Anchor system:

- Anchor interaction
- Activation state
- Heart restoration
- Respawn location
- Basic visual state change
