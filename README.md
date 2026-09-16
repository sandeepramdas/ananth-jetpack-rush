# Ananth's Jetpack Rush

A side-scrolling jetpack game built for Ananth, using his own caricature as the pilot.

**Play it:** https://sandeepramdas.github.io/ananth-jetpack-rush/

## How to play

Enter a pilot name, pick a map, then hold the mouse, tap and hold on a touchscreen,
or hold **Space** to fire the jetpack. Let go to drop. Dodge the electric beams and
the missiles, and collect bolts.

## What's in it

- **Five maps** — Sector 7 Lab, Neon City, Cryo Vault, Magma Core and Orbital Ring.
  Each one is a full re-skin: its own wall colours, parallax scenery (rain and lit
  windows, stalactites and frost, basalt and embers, a starfield and a passing
  planet) and its own nine level names. Pick one on the start screen, or flick
  through them with the arrow keys — the menu backdrop previews the choice live.
  Every gameplay number is identical across maps, so the scores stay comparable.
- **Levels** — start at Level 0 and climb through nine of them. Each level raises
  the speed, the hazard density and the music.
- **Leaderboard** — a top ten per map, kept in the browser's local storage. Any run
  that makes the cut is recorded straight away, and the crash card invites you to
  name it. Nothing leaves the device, so the board is per-browser.
- **Power-ups** — Shield (earned with bolts you fly into, and each one in a run costs
  more than the last, so a good run cannot chain them into permanent invulnerability),
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

A map is pure data: colour tokens plus one `deco()` function that draws its
mid-ground parallax band. `drawBackground()` and `drawStructure()` read those tokens,
so adding a sixth map means adding one entry to `MAPS`.

Rendering is HTML5 canvas. The game scales off the smaller screen dimension, so it plays
the same on a phone as on a desktop.

## Running locally

Open `index.html` in a browser. That's it.

---

Built with [Claude](https://claude.com/claude-code).
