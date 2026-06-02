# Worlds

Shellbound takes place across strange connected worlds joined by ancient beams, old pathways, and recurring turtle-shaped mysteries.

## Hub World - The Great Shell

The Great Shell is the return point, economy center, NPC gathering place, and beam travel hub.

The game should load directly into `_00_HubWorld` after required startup screens. The Great Shell is the first playable screen, not a menu backdrop.

Core features:
- Shellvis shop
- Grunk stall
- Beam platform
- Decoration areas
- Traveler space
- Settings and utility consoles

Hub evolution:
- NPCs from restored worlds migrate into the hub.
- Dialogue changes after beams are restored.
- Decoration areas fill with player choices.
- The hub should feel more alive after each world reconnects.

## Beam System

Ancient beams reconnect places that have drifted apart over time.

The player restores beams by exploring worlds, overcoming obstacles, defeating or resolving bosses, and returning connection to broken pathways.

## Beam Anchors

Each world contains several Beam Anchors.

Beam Anchors are ancient anchor-shaped structures connected to the beam network. They serve as the world's checkpoint system and give players a clear sense of safety, progress, and reconnection.

Functions:

- Checkpoint
- Respawn location
- Heart restoration
- Save point
- Navigation landmark
- Completion objective

When inactive, anchors are dirty, rusted, mossy, salt-stained, or covered in world-specific grime.

When activated, the player cleans/restores the anchor. The anchor becomes illuminated and visibly reconnected to the beam network.

Design goals:

- Anchors should be visible from a distance.
- Anchors should help players orient themselves.
- Anchors should feel like part of the world, not abstract game UI.
- Each world can theme its anchor grime/restoration around that world's identity.

## Shellvis and Grunk

Every world contains:

- One Shellvis location
- One Grunk location

These locations should feel naturally integrated into the world.

Examples:

Sunny Shore:
- Dockside stall
- Junk pile near the harbor

Endless Tracks:
- Train station kiosk
- Cargo sorting area

Forgotten Aquarium:
- Underwater market
- Flooded junk exchange

Players should begin noticing that Shellvis and Grunk are always present.

The game should never fully explain why.

## World Unlocking

World access should be tied to restored beams, hub progression, and exploration.

Open question:
- Does Grunk spending ever unlock world access, or should it stay cosmetic and hub-focused?

## World Completion

World completion can include:
- Restored beam
- Boss resolved
- Junk collected
- Bobbleheads found
- NPCs helped
- Optional lore discovered

## Fast Travel

Fast travel is not defined yet.

Possible direction:
- Restored beams become travel points.
- The Great Shell remains the main travel anchor.
- Loading transitions may eventually show the turtle running on a beam.

## Act I - Adventure

- Sunny Shore
- Endless Tracks
- Beam Forest

See [Sunny Shore](sunny-shore.md) for the first-world flow and vertical-slice structure.

## Act II - Wonder

- Forgotten Aquarium
- Sugarwind Highlands
- Skyward Shell

## Act III - Understanding

- Turtle Temple
- Turtles All The Way Down

## World Template

Each world should eventually define:
- Theme
- Mechanics
- Enemies
- Collectibles
- NPCs
- Boss
- Secrets
- Beam restoration goal
- Hub changes after completion

## World Feel

- Colorful and readable at first glance.
- Low-poly, chunky, and nostalgic.
- Built around movement routes, secrets, and playful collectibles.
- Hiding deeper lore for players who keep poking at the edges.

## Open Questions

- Which world best supports the vertical slice?
- How visibly connected should worlds be from the start?
- What does world completion look like in the UI?
