# Source assets

These are the originals the game was built from. They are already **embedded as
base64 data URIs inside `../index.html`**, so the game does not load them at
runtime — it needs no server and no network. They live here so the game can be
rebuilt or restyled later.

| File | What it is |
|---|---|
| `ananth-cutout-full.png` | Ananth's caricature with the background matted out, full resolution (873×1343) |
| `ananth-body-sprite.png` | The flying sprite used in-game, 234×360, quantised to 192 colours |
| `ananth-head.png` | The 360×360 head crop used for the crash close-up and the start-screen portrait |
| `faah.mp3` | Ananth's "faahhhh", re-encoded to mono 64 kbps |

## Rebuilding

The original artwork arrived as RGB with a transparency checkerboard **baked into
the pixels** rather than a real alpha channel. It was matted out in Python by
masking low-saturation, high-value pixels, keeping only the region connected to the
image border, eroding one pixel so the black outline survived, and softening the
alpha. `ananth-cutout-full.png` is the result of that step.

To swap in new artwork, replace the sprite and head PNGs, base64-encode them, and
substitute the two `data:image/png;base64,...` strings assigned to `heroImg.src`
and `headImg.src` in `index.html`.
