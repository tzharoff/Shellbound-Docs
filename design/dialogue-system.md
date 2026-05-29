# Dialogue System

## Purpose

The dialogue system should let Shellbound present clear NPC conversations, small weirdness beats, and state-reactive dialogue without turning the first prototype into a branching narrative tool.

Dialogue should stay brief. Shellbound is about playing, exploring, collecting, and moving through strange places, not stopping the player for long story scenes.

The first build should prove:

- Shellvis can introduce the cosmetic reward loop.
- Grunk can introduce junk conversion.
- The game can remember who the player has met.
- Dialogue can change after simple saved flags.
- Shellbound weirdness can appear without requiring lore explanation.

## V1 Scope

V1 dialogue is:

- Linear.
- State-reactive.
- Continue-prompt driven.
- Player-silent.
- Short.
- Persistent through local JSON save flags.

V1 dialogue is not:

- Branching conversation.
- Quest scripting.
- Full cutscene sequencing.
- Long exposition.
- Mandatory lore reading.
- Localization-ready production content.
- A complex custom editor.

## Writing Rules

V1 dialogue should follow these rules:

- Short sentences.
- One idea per line.
- Few lines per interaction.
- No lore dumps.
- No long tutorials.
- No repeated explanation after the player already understands.

Dialogue should do one useful job at a time:

- Point the player toward an action.
- React to something the player did.
- Deliver a joke.
- Hint at weirdness.
- Confirm that the world changed.

If an idea needs a paragraph to explain, it probably belongs in the docs, not in the player's text box.

## Tooling Decision

Default implementation path:

1. Evaluate Yarn Spinner in Unity.
2. Use Yarn Spinner if the free Unity package supports the needed runtime hooks cleanly.
3. Fall back to Unity-native ScriptableObjects only if Yarn creates more workflow or integration cost than it removes.

Yarn Spinner is acceptable if it supports:

- Custom Shellbound dialogue UI.
- Named conversation nodes.
- Variables or custom variable storage.
- Commands or events for setting flags.
- A workflow that does not require branching choices in V1.

If Yarn is not acceptable, the fallback should keep the same runtime boundaries:

- `DialogueTrigger`
- `DialogueController`
- `DialogueStateStore`

## Runtime Boundaries

### DialogueTrigger

Attached to an interactable NPC or object.

Responsibilities:

- Store the conversation ID or Yarn node name.
- Show or support an interaction prompt.
- Ask `DialogueController` to start dialogue.
- Do nothing if dialogue is already running.

### DialogueController

Owns dialogue flow.

Responsibilities:

- Start a conversation by ID.
- Advance lines through the continue input.
- End dialogue cleanly.
- Lock or constrain player movement during dialogue.
- Restore player control when dialogue ends.
- Report missing conversation IDs clearly in editor or logs.

### DialogueStateStore

Owns persistent dialogue flags.

Responsibilities:

- Load local JSON save data.
- Save named boolean flags.
- Read named boolean flags.
- Provide a small bridge to Yarn variables or the ScriptableObject fallback.

## Save Flags

First required flags:

- `met_shellvis`
- `met_grunk`
- `heard_grunk_weirdness`
- `junk_converted_once`
- `cosmetic_purchased_once`

The first save file can be small and expandable:

```json
{
  "flags": {
    "met_shellvis": true,
    "met_grunk": true,
    "heard_grunk_weirdness": true
  }
}
```

Use stable flag names. Do not rename flags casually once builds or test saves exist.

## First Prototype Content

### Shellvis First Meeting

Purpose:

- Introduce Shellvis.
- Establish the questionable merchant tone.
- Mention cosmetics without implying stat upgrades.
- Set `met_shellvis`.

Example beats:

- Shellvis greets the player as if they are already a customer.
- Shellvis implies the fake turtle costume is normal.
- Shellvis hints that Grunk is useful for buying expressive rewards.

### Shellvis Repeat

Purpose:

- Prove state-reactive dialogue.
- Confirm `met_shellvis` changed the conversation.

Example beats:

- Shellvis recognizes the player.
- Shellvis pushes cosmetics again.
- Shellvis uses a short repeatable line.

### Grunk First Meeting

Purpose:

- Introduce Grunk as junk appraiser.
- Establish that Grunk only says "Grunk."
- Set `met_grunk`.

Example beats:

- Grunk says "Grunk."
- Another NPC or UI context implies everyone understands.
- The player does not get an explicit explanation.

### Grunk Weirdness Beat

Purpose:

- Prove optional weirdness through basic interaction.
- Set `heard_grunk_weirdness`.

Example beats:

- Grunk says "Grunk."
- Shellvis or the interaction result treats this as a complete professional appraisal.
- The game moves on without explaining the joke.

## UI Behavior

Dialogue appears in a 2D overlay with:

- Portrait.
- Character name.
- Dialogue text.
- Continue prompt.

V1 can use static portraits. Low-frame portrait animation is a later polish step.

Typewriter text is optional. It should not block the first implementation.

## Validation Checklist

The dialogue prototype succeeds if:

- The player can start, advance, and exit Shellvis dialogue.
- Repeating Shellvis dialogue uses saved state.
- The player can start, advance, and exit Grunk dialogue.
- Dialogue lines are short and easy to read while playing.
- Conversations end before they feel like they are delaying movement.
- Grunk weirdness is understandable as a joke without explanation.
- Flags persist after scene reload or play mode restart.
- Dialogue cannot start twice at once.
- Ending dialogue restores player control.
- Missing conversation IDs produce a visible warning or error without crashing.

## Deferred

- Branching player choices.
- Boss intro title card implementation.
- Shop UI integration.
- Full localization.
- Dialogue editor tooling.
- Complex cutscene commands.
