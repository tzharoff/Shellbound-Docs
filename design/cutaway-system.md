# Cutaway System

## What It Is

A cutaway switches from the player's camera to a separate scene camera for a short moment, then switches back.

It is not a full cinematic. The world stays exactly as it is. The player is just shown a different angle before returning to control.

Cutaways should be short and earn the pause. If the player is being asked to stop and watch something, it needs to be worth it.

## When To Use One

Good reasons for a cutaway:

- A gate opens. Show it opening from a dramatic angle.
- The player reaches a new area. Give them a moment to see the scale of it.
- A boss appears. Introduce it before the fight.
- Something changes in the world. Confirm the change happened.

Bad reasons for a cutaway:

- Explaining story the player does not need to know yet.
- Showing off an area the player just came from.
- Delaying the player without a clear payoff.

## The VHS Aesthetic

Cutaways in Shellbound look like old VHS footage.

This is intentional. The tape overlay includes:

- Scanlines.
- A tracking band that scrolls across the screen.
- Slight image jitter and skew.

The overlay gets more intense based on what the player is doing with the tape controls.

This fits the PS1-era look of the game and makes cutaways feel like found footage rather than polished cinematics.

## Player Controls During Cutaways

The player is not locked out of input during a cutaway.

They have tape controls:

| Input | Keyboard | Gamepad | Effect |
|---|---|---|---|
| Pause / Resume | P | South button (A / Cross) | Freezes the cutaway |
| Fast Forward | . (period) | Right Trigger | Speeds up playback |
| Rewind | , (comma) | Left Trigger | Plays backward |
| Skip | Enter | Right Shoulder | Ends the cutaway immediately |
| Restart | Backspace | Left Shoulder | Replays from the beginning |

This is a design choice. The player should feel like they are watching something on their own terms, not being forced to sit through it.

If a cutaway is interesting, the player can pause and look around. If they have already seen it, they can skip it. If they missed something, they can rewind.

## Interactive Camera

During a cutaway the player can nudge the camera angle slightly.

The movement is limited by yaw and pitch limits so the player cannot spin the camera completely around. It is enough to look slightly left or right while the main scene plays.

When the player stops moving the camera input, it drifts back to center.

## The Level Event Bus

Cutaways are triggered by level events, not by direct script calls.

The event bus is a simple broadcast system:

- Any object can raise a named event. `LevelEventBus.Raise("event_id")`
- Any listener picks it up and responds.

This keeps triggers and reactions decoupled. The trigger does not need to know what happens when the event fires. The listener does not need to know what raised the event.

### LevelEventTrigger

A component placed on a collider in the world.

Two activation modes:

- **On interact.** Player presses the interact button near it.
- **On trigger enter.** Player walks into the collider zone.

Can be set to fire once or repeatedly.

### LevelEventCutawayListener

Listens for a specific event ID and calls Play on a CameraCutawayPlayer.

This is how a gate trigger starts a cutaway when the player approaches.

### LevelEventListener

A generic listener that fires a UnityEvent when an event ID is raised.

Used for non-cutaway responses: opening a door, spawning an enemy, changing a material.

## CutawayObjectMover

Moves a GameObject from one position to another in sync with the cutaway's progress.

Works with fast-forward, rewind, and pause automatically because it reads the cutaway's normalized playback position each frame.

Use this for things that should move during the cutaway, like a gate opening or a platform rising.

## The Sunny Shore Example

The Sunny Shore bell gate uses this system to introduce the gate before the player crosses it.

Setup:

1. Player walks toward the gate. An invisible trigger zone fires the `sunny_shore_bell_gate` event.
2. The cutaway listener hears the event and plays the cutaway.
3. The cutaway camera is positioned above and behind the gate, looking down at it.
4. A CutawayObjectMover moves the gate from closed to open during the cutaway.
5. The VHS tape overlay appears.
6. The player can pause, fast-forward, rewind, or skip at any point.
7. The cutaway ends and the player camera returns.

The bell object in the world also acts as a separate interact trigger so the player can replay the cutaway by ringing the bell again.

## Runtime Rig

For testing in the editor without placing assets manually, the `SunnyShoreCutawayRuntimeRig` script builds the full Sunny Shore cutaway setup at runtime when the Sunny_Shore scene is loaded.

It creates the cutaway camera, the event listener, the approach trigger, and the bell trigger in code.

This is a development convenience. Production scenes should have these objects placed as proper prefabs in the scene hierarchy.

## Rules

- Keep cutaways short. A few seconds is usually enough.
- Always give the player a reason to watch. If nothing meaningful is shown, skip the cutaway.
- Do not use cutaways to replace dialogue. Characters should still talk through the dialogue system.
- The VHS overlay is subtle during normal playback. It gets heavier during pause and shuttle. Do not crank it up just because it looks cool.
- The player can always skip. Design assuming they will.
