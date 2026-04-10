# Asterisk (Web Edition)

Asterisk is a fast, single-player reflex game where you guide a moving line through a field of obstacles. Your line constantly moves to the right, and you can only control vertical movement: hold a key to rise, release to fall.

This project is a browser-based port of the classic Asterisk concept, implemented as a single HTML file for easy use and sharing.

## What the Game Is

At its core, Asterisk is about rhythm and anticipation.

- You survive by steering one pixel-wide trail through open space.
- Every level adds more obstacles.
- Game speed increases as levels go up.
- If your trail touches anything that is not empty space, the run ends.

The game is simple to learn but quickly becomes challenging.

## Features

- Single-file web game (`index.html`)
- Three difficulty modes to start a run:
  - Easy
  - Normal
  - Hard
- 3-second countdown before each level starts
- Level-based speed increase (capped at level 10 speed)
- Obstacle field made of 2x2 blocks
- Left-edge start indicator showing where your line begins
- Crash explosion animation on collision
- Persistent high-score record (stored in browser localStorage)

## How to Run

No build tools or installation are required.

1. Open `index.html` in a modern web browser.
2. Select a difficulty to start.
3. Play.

You can also host the folder with any static file server, but it is not required.

## How to Play

### Goal

Reach the right side of the playfield to clear each level, then survive the next one.

### Controls

Hold any of these keys to move upward:

- Space
- Arrow Up
- Control
- Enter

Release the key to drift downward.

### Starting a Run

1. Click a difficulty button (Easy, Normal, or Hard).
2. Wait for the 3-second countdown.
3. Control begins when countdown reaches zero.

### Level Progression

- Each level starts at the left side of the screen.
- A small marker on the left border shows the exact starting height.
- Obstacle count grows with level.
- Speed gets slightly faster every level, up to level 10.
- After level 10, speed stays at the max for the selected difficulty.

### Losing Conditions

You lose immediately if your line touches:

- Any obstacle block
- Walls/border
- Any non-empty pixel in the playfield

On crash, a short explosion animation plays before game-over/high-score handling.

## Difficulty Modes

Difficulty affects both obstacle density and speed ramp.

- Easy: fewer obstacles and slower pace
- Normal: balanced default
- Hard: denser obstacles and faster pace

You choose a difficulty to start each run.

## High Scores

The game tracks best level reached and player name using browser storage.

- If you beat your best level, you are prompted to enter a name.
- Record persists between browser sessions on the same machine/browser profile.

## Tips for Better Runs

- Use short taps instead of holding too long.
- Look ahead and plan your vertical position early.
- Treat movement like a wave: small corrections beat big swings.
- During countdown, mentally map the closest obstacle cluster.
- On faster levels, commit to cleaner lines and avoid over-correcting.

## Technical Notes

- Rendering and collision use the canvas pixel surface.
- Game update loop is timer-driven with per-level tick timing.
- Visual effects (like crash burst) use requestAnimationFrame.
- Entire playable app is contained in one file for portability.

## Project Files

- `index.html`: Complete game (HTML, CSS, and JavaScript)
- `README.md`: This guide

## Future Enhancement Ideas

- Pause/resume
- Practice mode
- Seeded runs for replaying exact obstacle patterns
- Audio cues for countdown, level-up, and crash
- Stats dashboard (average level, total runs, best streak)
