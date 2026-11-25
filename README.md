# Skybolt

A small one-button browser game: guide **Bolt**, a round propeller robot, through gaps between crystal columns over a dusk landscape. Built with a single `index.html`, vanilla JavaScript and the Canvas API. No frameworks, no build step, no external assets.

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

## Features

- All art drawn with canvas shapes: propeller robot, crystal columns, parallax dusk sky, scrolling ground
- Fixed-timestep physics (120 steps/s), so it plays the same on 60 Hz and 120 Hz screens
- Gentle difficulty ramp: speed rises and gaps shrink with score, within set limits
- Synthesized sound effects (Web Audio API) with a mute toggle
- Scales to any screen and works with touch
