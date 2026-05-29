# Devlog 0004 - Validating The Dialogue System Plan

## Date

2026-05-29

## Summary

The next thing we want to plan is dialogue.

Dialogue is the text box that appears when the player talks to a character.

For Shellbound, dialogue needs to do a few simple jobs:

- Let characters talk.
- Let the player press a button to continue.
- Remember if the player has already met someone.
- Change a line of dialogue when something has already happened.
- Show a little bit of the game's weirdness without explaining everything.

It also needs to stay short.

This is a game about playing, exploring, collecting, and moving around.

We do not want the player drowning in story text.

We are starting small on purpose.

## Decision

The first dialogue system should be simple.

The player will walk up to a character, press a button, read a short line, and press a button to continue.

The player will not choose responses yet. The turtle stays quiet.

The game should remember small things, like:

- The player has met Shellvis.
- The player has met Grunk.
- The player has heard Grunk say "Grunk" and somehow everyone else understood it.

We will look at Yarn Spinner first because it is a Unity tool made for writing game dialogue.

If Yarn Spinner makes the job easier, we will use it.

If Yarn Spinner makes the job harder, we will build a smaller version ourselves.

Either way, the goal stays the same: make a simple dialogue box that can remember a few facts.

The writing rule is simple:

Short sentences. Few lines. Get the player back to the game.

## Assumption

We do not need a big dialogue system yet.

We do not need:

- Dialogue choices.
- Quest trees.
- Long cutscenes.
- A fancy editor.
- A huge story system.
- Long explanations.
- Lore dumps.

Those things can come later if the game actually needs them.

Right now, the important question is smaller:

Can the game show a character talking, remember that the conversation happened, and show different text next time?

## Validation Plan

We will test the idea with two characters: Shellvis and Grunk.

The test should prove:

- Shellvis can say hello the first time.
- Shellvis can say something shorter the next time.
- Grunk can say "Grunk."
- The game can treat "Grunk" like it meant something.
- The game can save that these conversations happened.
- The conversation ends before it feels like it is slowing the game down.

That is enough for the first test.

If that works, the system is useful.

If that feels annoying to write or hard to build, we change the plan before adding more characters.

## Result

The plan is accepted for implementation.

The first version should stay small until the Shellvis and Grunk test works.

No branching choices yet.

No quest system yet.

No boss intro system yet.

First we prove that normal talking works.

Normal talking should be quick.

## Follow-Up

When we build this in Unity, we should write another devlog entry about what happened.

That entry should answer:

- Did Yarn Spinner help?
- Did we build our own smaller system instead?
- Was it easy to write dialogue?
- Did the game remember the right things?
- What should new developers learn from this test?

## Lesson

A new system should be tested with the smallest useful example.

For dialogue, that does not mean writing the whole story.

It means making two characters talk, saving a few simple facts, and checking if the system feels good enough to keep using.

Start small. Prove the basics. Then build more.
