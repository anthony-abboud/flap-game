# Skybolt

A small one-button browser game: guide **Bolt**, a round propeller robot, through gaps between crystal columns over a dusk landscape. Built with a single `index.html`, vanilla JavaScript and the Canvas API. No frameworks, no build step, no external assets.

**▶ Play it:** https://anthony-abboud.github.io/flap-game

## Controls

| Action | Input |
| --- | --- |
| Flap | Click, tap, or **Space** |
| Mute / unmute | Speaker button (top right) or **M** |

## Run locally

Open `index.html` in any modern browser.

## Tuning

Gameplay and look are controlled by the `CONFIG` object at the top of the script in `index.html` (gravity, flap strength, gap size, scroll speed, parallax, and so on). Colors live in `PALETTE` right below it.

## Status

Stage 1: art preview (all characters, obstacles, background and ground drawn with canvas shapes). Gameplay comes next.
