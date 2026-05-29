# DDR-0004 - Dialogue V1 Uses Yarn If Acceptable

## Status

Accepted for prototype validation

## Decision

Shellbound's first dialogue implementation should evaluate Yarn Spinner as the default path.

If Yarn Spinner supports the needed Unity runtime hooks without forcing unwanted complexity, V1 dialogue should use Yarn.

If Yarn is too heavy for the current needs, the fallback is a small Unity-native ScriptableObject system with the same runtime boundaries:

- `DialogueTrigger`
- `DialogueController`
- `DialogueStateStore`

## Reason

Shellbound needs dialogue that can react to saved state, support recurring NPCs, and preserve a clean authoring path as content grows.

The game does not currently need branching player choices. The player turtle is silent, and V1 dialogue should be continue-prompt driven.

Yarn is worth evaluating because it is built for authored dialogue, named nodes, variables, and commands. It should only be adopted if those benefits outweigh the cost of adding an external narrative package.

## Validation Criteria

Yarn is acceptable if it supports:

- Custom Shellbound dialogue UI.
- Named NPC conversation nodes.
- Continue-prompt only flow.
- State-reactive dialogue through variables or custom variable storage.
- Commands or events for setting save flags.
- Local JSON persistence through a small save bridge.

## Consequences

- Dialogue implementation starts with a bounded tooling spike.
- The save flag layer must be implemented early.
- The runtime boundaries should stay stable even if Yarn is replaced.
- Branching choices stay deferred.
- Dialogue content can start with Shellvis and Grunk instead of a large story pass.
