# Devlog 0008 - Cutaway System

## Date

2026-05-30

## Summary

We built a cutaway system for Shellbound.

A cutaway is a short camera switch. The game cuts away from the player's view to a different camera angle to show something, then cuts back and returns control.

This is not a full cinematic. The world does not stop. The player is just briefly shown a different perspective.

## What We Built

### The Camera Switch

The cutaway system uses two cameras.

One is the player's normal camera. The other is a dedicated cutaway camera placed wherever it needs to be for that specific scene moment.

When a cutaway plays, the player camera turns off and the cutaway camera turns on. When it ends, they swap back. The player camera returns to exactly where it was.

### The Level Event Bus

Cutaways are not triggered by direct script calls. They are triggered by named events.

Any object in the scene can fire a named event. Any listener picks it up and responds.

This keeps things simple. A trigger near a gate fires an event called `sunny_shore_bell_gate`. A listener hears that event and plays the cutaway. The trigger does not care what the listener does. The listener does not care what fired the event.

Two trigger modes exist:

- The player walks into a zone. The event fires automatically.
- The player presses the interact button on an object. The event fires on demand.

Both can be active on the same object.

### The Tape Controls

This was a design choice.

The player is not locked out of input during a cutaway. They have tape controls, like an old VHS player.

They can:

- Pause the cutaway.
- Fast forward through it.
- Rewind it.
- Skip it entirely.
- Restart it from the beginning.

This respects the player's time. If they have seen the cutaway before, they can skip it. If they missed something, they can rewind. If they want to sit in the moment, they can pause and look around.

### The VHS Overlay

While a cutaway plays, a VHS tape effect appears on screen.

It shows scanlines, a tracking band that scrolls across the screen, and slight jitter and skew.

The effect gets more intense when the player pauses or shuttles the tape. A paused cutaway looks like a frozen VHS frame. Fast-forwarding adds more noise and streaks.

This fits the PS1 aesthetic of the game and makes cutaways feel like found footage rather than polished movie sequences.

### Object Mover

A simple component moves a world object from one position to another during a cutaway.

It reads the cutaway's current playback position and moves the object accordingly. If the player rewinds, the object moves backward. If they fast-forward, it moves faster.

Used for things like a gate opening, a platform rising, or a bridge extending.

### Sunny Shore Test

The system was tested with the Sunny Shore bell gate.

- Player walks toward the gate. A trigger zone fires the event.
- Cutaway plays. Camera shows the gate from above.
- Gate swings open during the cutaway.
- VHS tape overlay appears.
- Player can pause, fast-forward, rewind, or skip.
- Cutaway ends. Player camera returns.
- Player can also walk up to the bell and press interact to replay it.

The test scene builds itself at runtime for development convenience. When the Sunny Shore scene loads in the editor, it creates the cutaway camera, triggers, and listeners in code. No manual prefab setup required for testing.

## Key Decisions

**Cutaways, not cinematics.**

A cinematic takes over the game completely. A cutaway just borrows the camera for a moment.

Shellbound should stay movement-forward. If the player is stopped, it should be for a reason and it should be brief. Cutaways match this better than full cinematics.

**Players control the tape.**

Locking the player out of input during story moments feels disrespectful. The tape controls solve this. Players who want to experience the moment fully can. Players who want to skip can skip. Neither group is penalized.

**VHS fits the game.**

The tape noise and scanlines are not random. They connect cutaways to the overall PS1 and retro aesthetic. They also make cutaways feel slightly strange and old, which matches the tone of Shellbound's world.

**Events, not direct calls.**

Using a named event bus means triggers and reactions are independent. Adding a new response to an existing event does not require changing the trigger. This scales well as the world gets more complex.

## Open Questions

- How long should a cutaway be before it starts to feel too long?
- Should the VHS overlay appear during boss introductions, or is that a different treatment?
- Should players be able to disable the tape controls if they find them distracting?

## Next Session Goal

Build the shop system so Shellvis can sell cosmetics and the Grunk economy becomes a complete loop.
