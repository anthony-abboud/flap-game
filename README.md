# Clutch

A small Lehigh University–themed, one-button browser game: guide **Clutch**, a Mountain Hawk, between tree stumps across campus, by day (autumn) or by night (winter). Built with a single `index.html`, vanilla JavaScript and the Canvas API. No frameworks, no build step.

**▶ Play it:** https://anthony-abboud.github.io/flap-game

## Controls

| Action | Input |
| --- | --- |
| Flap / start / retry | Click, tap, **Space** or **↑** |
| Mute / unmute | Speaker button (top right) or **M** |
| Day / night mode | Sun/moon button (under the speaker) or **T** |

Pass between the stumps to score. Hitting a stump, the ground or the top of the screen ends the run. Your best score, mute setting and day/night choice are saved in your browser. Until you pick a mode, the game follows your device's light/dark setting.

## Run locally

The game loads image files, so serve the folder rather than opening `index.html` directly, for example with `python -m http.server` in this folder and then http://localhost:8000.

## Tuning

Everything is in the `CONFIG` object at the top of the script in `index.html`. Sizes are given as fractions of the 480×720 playfield:

| Setting | Default | What it does |
| --- | --- | --- |
| `columnWidth` | 8% of width | Stump trunk width (and hitbox width) |
| `startGap` / `minGap` / `gapPerPoint` | 25% of height / 150 / 1 | Opening between the stumps, shrinking gently with score |
| `spacingMin` / `spacingMax` | 34% / 49% of width | Random centre-to-centre distance between pairs |
| `climbRate` / `dropRate` | 180 / 260 px/s | How far the opening may move between pairs, given the time Clutch has to get there |
| `campusScrollRatio` | 0.3 | Campus speed as a fraction of the stump speed |
| `startSpeed` / `maxSpeed` / `speedPerPoint` | 150 / 220 / 2 | Stump and ground speed |

Clutch and UI colours live in `PALETTE`; per-theme background and ground colours live in `THEMES`.

## Art

- **Clutch:** `sprites/clutch-1.png` to `clutch-3.png` are the wing-beat frames (up, level, down), smaller copies of the originals in `sprites/source/`. They play in the order listed in `SPRITE.frames`, and each flap jumps to the downstroke. `SPRITE.width`, `anchorX` and `anchorY` set the size and where the hitbox sits. If the images fail to load, the game draws a built-in hawk.
- **Stumps:** cut from `sprites/source/stumps-original.png` into a cut end and a bark section for each stump (`sprites/stump-*.png`). The cut end is always drawn at its original proportions; the bark repeats to make the stump as long as needed.
- **Campus:** `backgrounds/campus-autumn.jpg` (day) and `backgrounds/campus-winter-night.jpg` (night), from the originals in `backgrounds/source/`. The picture's left and right edges don't match, so it loops as picture → mirrored picture → picture, which joins seamlessly.
- **Ground:** pixel-art grass and dirt drawn in code.

## Features

- Uneven spacing and varied gap heights, always within reach of the previous gap
- Campus background scrolls at 30% of the stump speed on its own loop, independent of stump spawning
- Day and night modes
- Fixed-timestep physics (120 steps/s), so it plays the same on 60 Hz and 120 Hz screens
- Gentle difficulty ramp: speed rises and gaps shrink with score, within set limits
- Synthesized sound effects (Web Audio API) with a mute toggle
- Scales to any screen and works with touch
