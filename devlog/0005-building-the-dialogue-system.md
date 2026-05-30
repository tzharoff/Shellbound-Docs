# Devlog 0005 - Building the Dialogue System

## Date

2026-05-30

## Summary

We built the dialogue system from scratch.

This is the system that makes characters talk to the player.

It also remembers what has already happened, and it can change what a character says based on what the player is wearing.

## What We Built

The dialogue system has three jobs.

**Job one: show a conversation.**

Each character has a list of conversations. When the player presses the interact button near a character, the game picks the right conversation and shows it on screen. The player presses the button again to move through the lines. The last press closes the box.

**Job two: pick the right conversation.**

Characters do not always say the same thing. Each conversation has a list of conditions. The game checks the conditions from top to bottom and picks the first conversation where all conditions pass.

This works like layers. The most specific reaction goes at the top. The default greeting goes at the bottom.

Two condition types exist right now:

- Flag condition. Checks whether something has already happened. For example: has the player already met Shellvis?
- Cosmetic condition. Checks whether the player is wearing a specific item. For example: is the player wearing the Emperor's New Shell?

This is how the Emperor's New Shell will work. Shellvis sees the player wearing it and reacts with awe. The player sees nothing unusual. The game never explains it.

**Job three: remember what happened.**

When a conversation ends, the game can set named flags. Flags are simple yes or no values saved to the player's file.

Examples: met_shellvis, met_grunk, heard_grunk_weirdness.

These flags feed back into the condition system. Next time the player talks to Shellvis, the flag is set, so the second conversation plays instead of the first.

## Key Decisions

**ScriptableObjects over Yarn Spinner.**

Yarn Spinner is an external tool made for dialogue. The dialogue system here is simple enough that building it directly in Unity was faster and easier. No external dependency. Everything lives in the project.

**Conditions work like layers.**

Each NPC has an ordered list of conversations. The first one whose conditions all pass is the one that plays. This means reactions to specific things go at the top, and the fallback always goes at the bottom.

This is flexible. Later on, adding a new reaction to any character is just adding a new entry at the right position in the list.

**One interact button for everything.**

The player uses the same button to start a conversation and to move through it. Press near a character to start. Press again to advance. No separate buttons.

If the typewriter is still printing when the player presses, it jumps to the end of the line. The next press advances.

**The player turtle never speaks.**

There are no dialogue choices. No response options. The turtle is quiet. The game stays short and keeps moving.

## How the Pieces Fit Together

- DialogueFlag is an asset that represents a named boolean. Drag it into a condition or a conversation to use it.
- DialogueSpeaker is an asset that holds a character's name, portrait, and name colour.
- DialogueLine is a single line of text attached to a speaker.
- DialogueConversation is a list of lines and the flags to set when it ends.
- DialogueCondition is the base type for all conditions. FlagCondition and CosmeticEquippedCondition are the two types built so far.
- DialogueTrigger goes on an NPC. It holds the ordered conversation list and handles the interaction.
- DialogueController is the scene manager. It runs conversations, advances lines, and fires events.
- DialogueStateStore is the dialogue-facing wrapper for reading and writing flags.

## Open Questions

- When will Shellvis and Grunk have actual art and be placed in the hub?
- What does the Emperor's New Shell cosmetic look like visually?
- How many conversations will each character need for the vertical slice?

## Next Session Goal

Build the save system so dialogue flags, Grunk balance, and equipped cosmetics survive between sessions.
