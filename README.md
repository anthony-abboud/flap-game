# Clutch

A small Lehigh University–themed, one-button browser game: guide **Clutch**, a Mountain Hawk, through gaps between crystal columns over a dusk landscape. Built with a single `index.html`, vanilla JavaScript and the Canvas API. No frameworks, no build step. The only image file is Clutch's sprite; everything else is drawn in code.

**▶ Play it:** https://anthony-abboud.github.io/flap-game

## Controls

| Action | Input |
| --- | --- |
| Flap / start / retry | Click, tap, **Space** or **↑** |
| Mute / unmute | Speaker button (top right) or **M** |

Pass between the crystal columns to score. Hitting a crystal, the ground or the top of the screen ends the run. Your best score is saved in your browser.

## Run locally

Open `index.html` in any modern browser.

## Tuning

Gameplay and look are controlled by the `CONFIG` object at the top of the script in `index.html` (gravity, flap strength, gap size, scroll speed, parallax, and so on). Colors live in `PALETTE` right below it.

## Clutch's sprite

`sprites/clutch-1.png` is the in-game sprite, a smaller copy of the original drawing in `sprites/source/`. To animate the wings, add more frames (same canvas size, body in the same spot, facing right) and list them in `SPRITE.frames` in `index.html`. `SPRITE.width`, `anchorX` and `anchorY` set the size and where the hitbox sits on the image. If the images fail to load, the game draws a built-in hawk instead.

## Features

- All art drawn with canvas shapes: Clutch the hawk, crystal columns, parallax dusk sky, scrolling ground
- Fixed-timestep physics (120 steps/s), so it plays the same on 60 Hz and 120 Hz screens
- Gentle difficulty ramp: speed rises and gaps shrink with score, within set limits
- Synthesized sound effects (Web Audio API) with a mute toggle
- Scales to any screen and works with touch
