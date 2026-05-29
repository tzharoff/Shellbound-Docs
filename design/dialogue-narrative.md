# Dialogue And Narrative

## Story Overview

A small turtle leaves home after a mysterious disappearance, restores ancient beams, reconnects distant worlds, and searches for the Great Turtle.

The surface story should stay clear and playable. The deeper story can be stranger, quieter, and optional.

## Narrative Rules

- The player should always understand the immediate goal.
- Playing should matter more than reading.
- Dialogue should use short sentences.
- Most story should be implied through action, places, characters, and changes in the world.
- Deeper lore should reward curiosity.
- Weirdness should be subtle, not homework.
- Some characters may remember things differently.
- Time can be unreliable.
- The player may perceive the world differently than surrounding characters.

## Reality Perception

The player occasionally perceives the world differently than surrounding characters.

Examples:
- Emperor's New Shell
- Understanding Grunk
- Optional dialogue interpretation

This should remain subtle and never become the main plot.

## Dialogue System

Dialogue appears in a 2D overlay.

Characters display:
- Portrait
- Name
- Dialogue
- Optional prompt

Portraits use simple animation. No full facial animation.

See [Dialogue System](dialogue-system.md) for the build-facing V1 runtime plan.

V1 dialogue is linear, state-reactive, and continue-prompt driven. The player turtle does not speak or choose responses in the first implementation.

The first prototype should validate Shellvis and Grunk interactions before expanding into boss introductions, optional lore sequences, or more complex NPC behavior.

## Dialogue Writing Rules

- Keep lines short.
- Prefer one idea per line.
- Avoid long explanations.
- Avoid lore dumps.
- Let the player return to movement quickly.
- Use dialogue to point, joke, react, or hint.
- Put deeper story in optional details, repeated patterns, and world changes.

Good Shellbound dialogue should feel like a quick interaction, not a reading assignment.

## Portrait Animation Style

Portraits use limited animation inspired by:
- Puppets
- Retro RPGs
- Low-frame character portraits

Animation examples:
- Mouth flap
- Blink
- Slight movement
- Idle loops
- Simple eye movement

## Dialogue Layout

```txt
+--------------------+
| [ Portrait ]        |
|                    |
| SHELLVIS           |
|                    |
| Excellent choice.  |
|                    |
| > Continue         |
+--------------------+
```

## Boss Introductions

Trigger:
- Boss encounter

Presentation:
- Dramatic overlay
- Anime speed lines
- Title card
- One-liner

Example:

```txt
GREAT RED LOBSTROCITY

"Red remember."

Fight starts.
```

## Time Is Funny Here

Time weirdness should appear through character memory, repeated encounters, changed dialogue, and places that feel older than they should.

The Kid is the main emotional anchor for this idea.

## Optional Lore

Optional lore should be findable through:
- Recurring dialogue
- Symbol patterns
- Shellbert interactions
- Boss phrases
- Hub changes
- Environmental details
