# Clutch

A small Lehigh University–themed, one-button browser game: guide **Clutch**, a Mountain Hawk, through gaps between snowy mountain peaks, by day or by night. Built with a single `index.html`, vanilla JavaScript and the Canvas API. No frameworks, no build step. The only image file is Clutch's sprite; everything else is drawn in code.

**▶ Play it:** https://anthony-abboud.github.io/flap-game

## Controls

| Action | Input |
| --- | --- |
| Flap / start / retry | Click, tap, **Space** or **↑** |
| Mute / unmute | Speaker button (top right) or **M** |
| Day / night mode | Sun/moon button (under the speaker) or **T** |

Pass between the mountain peaks to score. Hitting a peak, the ground or the top of the screen ends the run. Your best score, mute setting and day/night choice are saved in your browser. Until you pick a mode, the game follows your device's light/dark setting.

## Run locally

Open `index.html` in any modern browser.

## Tuning

Gameplay and look are controlled by the `CONFIG` object at the top of the script in `index.html` (gravity, flap strength, gap size, scroll speed, parallax, and so on). Clutch and UI colors live in `PALETTE` right below it; day and night scenery colors (sky, sun, moon, clouds, hills, grass, dirt, peaks) live in `THEMES`.

## Clutch's sprite

`sprites/clutch-1.png` to `clutch-3.png` are the wing-beat frames (up, level, down), smaller copies of the original drawings in `sprites/source/`. They play in the order listed in `SPRITE.frames` in `index.html`, and each flap jumps to the downstroke. New frames should keep the same canvas size, with the body in the same spot, facing right. Wing-beat speed is set by `wingBeatSpeed` and `flapWingSpeed` in `CONFIG`. `SPRITE.width`, `anchorX` and `anchorY` set the size and where the hitbox sits on the image. If the images fail to load, the game draws a built-in hawk instead.

## Features

- Pixel-art mountain peaks generated in code, so every peak is different (snow caps, rock ledges, pine trees)
- Pixel-art day and night scenery in the same style as Clutch: sun or moon and stars, clouds, layered hills with parallax, grass and dirt
- Fixed-timestep physics (120 steps/s), so it plays the same on 60 Hz and 120 Hz screens
- Gentle difficulty ramp: speed rises and gaps shrink with score, within set limits
- Synthesized sound effects (Web Audio API) with a mute toggle
- Scales to any screen and works with touch
