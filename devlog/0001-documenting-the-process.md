# Devlog 0001 - Documenting The Process

## Date

2026-05-28

## Summary

This project is not using a traditional single game design document as its main source of truth.

Instead, Shellbound will be documented as a living development record: design notes, decision records, validation notes, production planning, and devlog entries that show how the game changes over time.

The goal is to create the game and document the process clearly enough that budding game developers can learn from the decisions, mistakes, experiments, and revisions along the way.

## Decision

Shellbound's documentation will be built around a decision loop:

1. Make a design or production decision.
2. Explain the reason for that decision.
3. Validate the decision through prototyping, playtesting, comparison, or review.
4. Record what happened.
5. Keep, revise, or cut the decision based on what was learned.

The devlog will not only describe what was worked on. It will explain why choices were made, how those choices were tested, and what changed afterward.

## Why

A traditional game design document is useful for describing a planned game, but it can hide the process that produced the final design.

For this project, the process matters. New developers often see finished mechanics, polished trailers, or postmortems written after the fact. They do not always see the uncertain middle: the small assumptions, the messy prototypes, the ideas that seemed good until tested, or the design changes that came from a specific problem.

Shellbound's devlog should make that middle visible.

## Documentation Structure

The repository will separate current truth from historical process:

- `design/` describes the current design of the game.
- `decisions/` records major design decisions and their rationale.
- `production/` tracks planning, milestones, risks, and backlog items.
- `reference/` stores shared vocabulary, naming notes, cut ideas, and supporting material.
- `devlog/` explains the development journey over time.

This keeps the docs useful in two ways:

- Developers can read the design docs to understand what Shellbound currently is.
- Learners can read the devlog to understand how Shellbound got there.

## Validation Plan

Each major design choice should eventually be validated by at least one of the following:

- A playable prototype.
- A focused playtest.
- A comparison against the project's design pillars.
- A production review.
- A technical feasibility check.
- A content or scope review.

Not every decision needs a full playtest, but every important decision should have some kind of evidence behind it.

## Devlog Format

Future devlog entries should aim to include:

- What decision or problem the entry is about.
- Why the topic mattered.
- What assumption was being tested.
- What was built, written, changed, or reviewed.
- What was learned.
- What happens next.

The format can stay flexible, but the purpose should stay consistent: make the thinking visible.

## Key Decisions

- The project will use living markdown docs instead of one static design document.
- The devlog will be part production journal and part learning resource.
- Decisions should be validated before being treated as stable.
- The documentation should preserve the reason behind changes, not just the final answer.
- The audience includes future developers who want to understand how a game takes shape.

## Open Questions

- How often should devlog entries be written?
- Which decisions deserve a formal decision record?
- What level of detail is useful without turning the devlog into busywork?
- How will prototype results be captured once playable builds exist?

## Next Session Goal

Establish the initial foundation for Shellbound:

- High concept
- Core pillars
- Player experience goals
- Core loop
- Major characters
- Early progression philosophy
