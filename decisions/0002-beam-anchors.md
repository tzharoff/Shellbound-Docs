# DDR-0002 - Beam Anchors

## Status

Accepted

## Decision

Beam Anchors are the checkpoint and respawn system for Shellbound.

Each world contains multiple Beam Anchors. These are large ancient anchor-shaped structures tied into the beam network.

Activating a Beam Anchor:

- Creates or updates the player's respawn point inside the current world
- Restores the player's hearts
- Saves world progress
- Reconnects part of the beam network
- Cleans/restores the physical anchor

When the player loses all hearts:

- The player respawns at the most recently activated Beam Anchor in the current world
- Hearts are restored
- No Grunk is lost
- No traditional life is consumed
- The player is not sent back to the hub

## Reason

Shellbound is built around joyful movement, curiosity, and exploration.

Traditional lives and heavy death penalties could discourage players from experimenting, exploring, or checking strange corners of the world.

Beam Anchors provide a light consequence for failure while keeping the player inside the adventure.

## Narrative Role

Worlds in Shellbound have drifted apart over time.

Anchors help keep things from drifting.

Beam Anchors are physical manifestations of the beam network and act as:

- Checkpoints
- Respawn points
- Health restoration points
- Visual landmarks
- Symbols of reconnection

## Visual Direction

Inactive Beam Anchors should look:

- Rusty
- Mossy
- Salt-stained
- Ancient
- World-worn
- Dim or dormant

Active Beam Anchors should look:

- Cleaned
- Restored
- Warmly illuminated
- Connected to beam energy
- Slightly magical
- Easy to identify from a distance

## Consequences

- Worlds need deliberate Beam Anchor placement.
- Beam Anchors should be visible landmarks.
- Respawn design should support exploration, not punish it.
- Anchor restoration can contribute to completion tracking.
- Anchor restoration can unlock cosmetics.
