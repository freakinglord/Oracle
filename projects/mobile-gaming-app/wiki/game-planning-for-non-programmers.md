---
title: Game Planning for Non-Programmers
tags:
  - game-design
  - godot
  - gdscript
  - planning
source: "[[game-planning-for-non-programmers-idea]]"
source_type: raw
created: 2026-08-03
updated: 2026-08-08 18:17
---

# Game Planning for Non-Programmers

## Overview
A structured framework for planning and building a mobile asteroid survival game as a non-programmer with scripting familiarity: define the core loop, break it into 5 systems, pick an engine, plan the difficulty curve, and build in a fixed weekly order.

## Key Points

- **Core loop (one sentence)**: "Survive as long as possible by shooting asteroids before they hit your ship." Every feature added must serve this sentence.
- **Game concept**: dual-joystick controls — right joystick moves the ship in 2D space, left joystick aims/fires in all directions; one-hit death (like Flappy Bird); score = survival time.
- **5 systems** (build one completely before starting the next): ship movement, gunner/turret, asteroid spawner, collision detection, score/timer.
- **Engine choice**: Godot 4 recommended — free, GDScript ≈ Python, lightweight, mobile export, joystick support. Alternatives: Unity (C#, steeper learning curve), Construct 3/GDevelop (event-based, no code, fastest prototype but less flexible).
- **Difficulty curve ("Flappy Bird Factor")**: first 10 seconds slow/sparse; speed increases every 15-20 seconds; asteroid count increases over time; random sizes create unpredictable hitboxes.
- **One-hit death feedback**: needs dramatic explosion, score flash, and one-tap restart — restart speed drives addictiveness.
- **7-week build order**: Week 1 static ship + joystick input reading; Week 2 ship movement feels good; Week 3 gunner rotates and fires; Week 4 asteroids spawn and move toward ship; Week 5 collision = death + restart screen; Week 6 score timer + difficulty scaling; Week 7 juice (explosions, sounds, screen shake).
- **Getting started**: download Godot 4 (godotengine.org), follow one beginner tutorial to learn the editor, build systems strictly in order.

## Related
- [[mobile-gaming-app-index]] — Mobile Gaming App project index.

## Open questions / gaps
- No specifics yet on monetization, art/asset sourcing, or platform submission (iOS/Android store) process — worth ingesting if/when that planning happens.
