# Shellbound

**Restore the beams. Gather the Grunk. Leave the beam on for the next one.**

Shellbound is a nostalgic PS1-inspired third-person adventure collectathon where players explore strange connected worlds, gather valuable junk, and restore ancient beams in search of the Great Turtle.

## Project Status

**Early concept / pre-prototype**

This repository is the markdown-only design home for Shellbound. It contains the living game design breakdown, devlogs, production notes, decision records, and reference material.

No app framework. No docs generator. No package manager. Just editable markdown and the occasional deeply suspicious turtle costume.

## Title Page

- **Game:** Shellbound
- **Genre:** Third-person adventure collectathon
- **Feel:** PS1 / early 64-bit nostalgia, cozy adventure, strange humor, optional deeper lore
- **Core fantasy:** Be a small turtle exploring big connected worlds that existed long before you arrived
- **Progression model:** Expression, cosmetics, collection, hub life, and understanding instead of stat power
- **Startup flow:** Load through studio / engine screens, then enter `_00_HubWorld` directly
- **Current design source:** `Shellbound_GDD_Updated_Canon_v2.docx`

## Game Design Table Of Contents

### Foundation

- [Vision](design/vision.md) - High concept, target experience, tone, and scope.
- [Elevator Pitch](design/elevator-pitch.md) - One-sentence, short, and full descriptions.
- [Pillars](design/pillars.md) - The core design rules that keep the game honest.
- [Core Loop](design/core-loop.md) - The main play loop from exploration to expressive rewards.
- [Gameplay](design/gameplay.md) - Moment-to-moment breakdown, session flow, and completion philosophy.

### Player And Systems

- [Player](design/player.md) - Player character, inputs, health questions, and controller feel.
- [Movement](design/movement.md) - Run, jump, Shell Dash, slingshot traversal, and camera feel.
- [Economy](design/economy.md) - Junk, Grunk the character, Grunk the currency, and Shellvis spending.
- [Progression](design/progression.md) - Collectibles, unlocks, endgame, and replayability.

### World And Story

- [Worlds](design/worlds.md) - Hub, beam system, world unlocking, acts, and world list.
- [Characters](design/characters.md) - Player turtle, Shellvis, Grunk, Shellbert, The Kid, bosses, and The Great Turtle.
- [Enemies](design/enemies.md) - Enemy philosophy, standard enemies, elites, bosses, and difficulty.
- [Dialogue And Narrative](design/dialogue-narrative.md) - Story rules, dialogue UI, boss intros, time weirdness, and optional lore.

### Presentation And Technical

- [UI / UX](design/ui-ux.md) - HUD, dialogue UI, inventory, shop, pause, and accessibility.
- [Audio](design/audio.md) - Music direction, world themes, sound effects, and character voices.
- [Art Direction](design/art-direction.md) - PS1 style guide, environments, characters, animation, and post processing.
- [Technical Design](design/technical-design.md) - Engine, architecture, save data, data structure, and performance.
- [Vertical Slice](design/vertical-slice.md) - Scope, success metrics, required features, and stretch goals.

### Production

- [Roadmap](production/roadmap.md)
- [Milestones](production/milestones.md)
- [Backlog](production/backlog.md)
- [Risks](production/risks.md)

### Decisions And Reference

- [DDR-0001 - Progression Is Expression](decisions/0001-progression-is-expression.md)
- [DDR-0002 - Shellvis Sells, Grunk Converts](decisions/0002-shellvis-sells-grunk-converts.md)
- [DDR-0003 - Start In Hub World](decisions/0003-start-in-hub-world.md)
- [Glossary](reference/glossary.md)
- [Naming](reference/naming.md)
- [Cut Ideas](reference/cut-ideas.md)

### Devlog

- [Devlog 0001 - Foundations](devlog/0001-foundations.md)

## Folder Guide

- `design/` - Living GDD sections split into small markdown files.
- `production/` - Roadmap, milestones, backlog, and project risk notes.
- `decisions/` - Design decision records for choices that should stay visible.
- `reference/` - Shared vocabulary, naming notes, cut ideas, and appendix-like material.
- `devlog/` - Session notes and progress updates.
