<!-- GitHub topics: neon-breaker, breakout-game, html5-game, canvas-game, arcade-game, javascript-game, single-file-game, retro-games -->

# 🧱 Neon Breaker

A neon-soaked HTML5 Breakout arcade game in a **single file** — no build step, no dependencies, no install. Just open it in a browser and play.

![Screenshot placeholder: add a screenshot of the game in action here as `screenshot.png`]

## How to play

**Run it:**

```bash
# Option 1: just open the file
open neon-breaker.html

# Option 2: serve it locally (any static server works)
npx serve .
# then open http://localhost:3000/neon-breaker.html
```

That's it. Everything — game logic, graphics, sound — lives inside `neon-breaker.html`.

**Controls:**

| Key / Input      | Action              |
| ---------------- | ------------------- |
| Mouse            | Move the paddle     |
| ← / → arrows     | Move the paddle     |
| Space / ↑ / Enter| Launch the ball / start |
| P                | Pause               |
| M                | Mute / unmute sound |

## Features

- **8 hand-designed levels** — First Contact, Checkerboard, Crossfire, Pillars, Invader, The Diamond, The Fortress, and the finale, Neon Core
- **6 power-ups** — Wide paddle, Multi-ball, Slow ball, Extra life, Laser, and Sticky paddle
- **Synthesized sound effects** — generated in-browser with the Web Audio API (no audio files needed)
- **Combo scoring** — chain brick breaks to multiply your score
- **Persistent high score** — saved in your browser via `localStorage`
- **Neon visuals** — glowing bricks, particles, and a dark arcade aesthetic, all drawn on `<canvas>`

## How it works

The whole game is one HTML file (~33 KB):

- **Rendering:** Canvas 2D with glow effects
- **Audio:** Web Audio API oscillators — no assets
- **State:** levels, bricks, ball physics, paddle, power-ups, and particles in plain JavaScript
- **Persistence:** `localStorage` for the high score only — no accounts, no tracking

Open `neon-breaker.html` in any text editor to read or modify it. Levels are defined as a data array near the top of the script, so adding a new level is just adding a new entry.

## Customizing

- **New levels:** add an entry to the `LEVELS` array (name + brick layout)
- **New power-ups:** add an entry to the power-up definitions (name + color + effect)
- **Difficulty:** tweak ball speed, paddle width, and level layouts in the same script

## License

MIT — see [LICENSE](LICENSE). Free to play, fork, and build on.

## Author

Syed Shahid / Syed Ventures
