# Ananth's Jetpack Rush

A side-scrolling jetpack game built for Ananth, using his own caricature as the pilot.

**Play it:** https://sandeepramdas.github.io/ananth-jetpack-rush/

## How to play

Hold the mouse, tap and hold on a touchscreen, or hold **Space** to fire the jetpack.
Let go to drop. Dodge the electric beams and the missiles, and collect bolts.

## What's in it

- **Levels** — start at Level 0 and climb through Warm-Up, Service Tunnel, Lower Lab,
  Coolant Line, Reactor Row, Test Range, Black Sector, Overdrive and Meltdown. Each
  level raises the speed, the hazard density and the music.
- **Power-ups** — Shield (earned with 30 bolts, 15 seconds of flying through anything),
  Magnet (pulls every coin on screen), 2x Bolts, and Slip-Mo (slows the world down).
- **Seven original soundtracks** — five that swap as the levels climb, plus two that take
  over while a power-up is running. All generated live in the browser; no audio files.
- **Bolt streaks** — chain pickups for a rising run of notes and a multiplier.
- **FAAHH** — crash and you get Ananth's own voice, full screen.

## Technical notes

Everything is in a single `index.html` — no build step, no dependencies, no server.
The character artwork and the voice clip are embedded as data URIs, so the page is
completely self-contained. The whole soundtrack is synthesised at runtime with the Web
Audio API using a lookahead scheduler.

Rendering is HTML5 canvas. The game scales off the smaller screen dimension, so it plays
the same on a phone as on a desktop.

## Running locally

Open `index.html` in a browser. That's it.

---

Built with [Claude](https://claude.com/claude-code).
