# Game Planning for Non-Programmers

> Source: Exported Claude chat conversations
> Added: 2026-05-22
> Project: Mobile Gaming App

## Summary

A structured framework for planning and building a mobile asteroid survival game as a non-programmer with scripting familiarity. The core approach: define a one-sentence game loop, break it into 5 systems, choose Godot Engine (GDScript is Python-like), plan the difficulty curve, and build systems one at a time in a 7-week build order.

## Details

### The Game Concept

Dual-joystick asteroid survival game:
- **Right joystick** → moves ship in 2D space
- **Left joystick** → aims and fires in all directions
- **One-hit death** mechanic (like Flappy Bird)
- Score = survival time

### Phase 1 — Core Loop (One-Sentence Test)

Every great game fits into one sentence. Define it first; every feature added must serve it:

> *"Survive as long as possible by shooting asteroids before they hit your ship."*

### Phase 2 — The 5 Systems

| System | What it does |
|---|---|
| **Ship movement** | Right joystick moves ship in 2D space |
| **Gunner/turret** | Left joystick aims + fires bullets |
| **Asteroid spawner** | Spawns from all edges, escalating over time |
| **Collision detection** | Asteroid hits ship → instant death |
| **Score/timer** | Counts survival time |

Build one system at a time, completely, before starting the next.

### Phase 3 — Engine Choice

| Engine | Notes |
|---|---|
| **Godot 4** *(recommended)* | Free, GDScript ≈ Python, lightweight, mobile export, joystick support |
| Unity | Industry standard, C#, steeper learning curve |
| Construct 3 / GDevelop | Event-based (no code), fastest prototype, less flexible |

**Godot** is the sweet spot for script-familiar non-programmers.

### Phase 4 — Difficulty Curve (The Flappy Bird Factor)

Flappy Bird's genius: predictable but always punishing. Apply the same principle:
- First 10 seconds: asteroids start **slow and sparse** — feels easy
- Every 15–20 seconds: **speed increases** slightly
- Asteroid count increases over time
- Random sizes = unpredictable hitboxes

One-hit death requires instant, satisfying feedback: dramatic explosion, score flash, one-tap restart. Restart speed is critical to addictiveness.

### Phase 5 — 7-Week Build Order

```
Week 1 → Static ship on screen + joystick input reading
Week 2 → Ship movement feels good
Week 3 → Gunner rotates and fires bullets
Week 4 → Asteroids spawn and move toward ship
Week 5 → Collision = death + restart screen
Week 6 → Score timer + difficulty scaling
Week 7 → Juice it up (explosions, sounds, screen shake)
```

### Getting Started

1. Download Godot 4 (free at godotengine.org)
2. Follow one "Godot beginner" YouTube tutorial to learn the editor
3. Build systems in order — don't start Week 2 until Week 1 is working

## Key Points
- Define core loop first (one sentence) — every feature must serve it
- 5 systems are all you need; build one completely before starting the next
- Godot is the right engine for scripters — GDScript is Python-like
- Difficulty curve: start easy, escalate gradually, random sizes keep it unpredictable
- One-hit death requires fast restart loop — the restart speed drives addiction

## Related Topics
- [[index]]
