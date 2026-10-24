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

## Monetization

`neon-breaker-ads.html` is the same game with ads added — the game script
is byte-identical to `neon-breaker.html` (verified by diff + `node --check`),
so gameplay, levels, and power-ups are untouched. Only the page around the
game changed.

**Ad slots (Google AdSense):**

- **Above the game** and **below the game** — responsive display units.
  They sit outside the game container, so they can **never overlap the
  canvas, the pause/mute buttons, or the controls**.
- Publisher ID: `ca-pub-7363635746119645` (already in the file).
- **Before you publish:** open the file and replace both
  `data-ad-slot="0000000000"` placeholders with real ad slot IDs from your
  AdSense dashboard (Ads → By ad unit → Display ads). Each slot is marked
  with a `TODO` comment in the file. Until you do this, the units will not
  serve ads.
- **Policy rules baked into the layout:** no ads over gameplay, no
  "click the ad to continue" or any other click incentive, no gating
  gameplay behind ads. Keep AdSense Auto ads **off** for this page until
  the two manual slots are verified, so no auto-placed unit can land over
  the game.

**House-ad strip (always visible):**

Below the bottom ad slot sits a gold-bordered **"From Syed Ventures"**
strip promoting the author's own Gumroad products — Practice Pack
($14.99), Math Workbook ($9.99), Cheat Sheets ($7.99). It is labelled as
the author's own products, not disguised as a Google ad, and it shows
even when AdSense doesn't fill — so the page always earns attention.
Links open in a new tab so the game is never interrupted.

**Honest expectation:** AdSense pays only after the account is fully
approved and the page gets real traffic. An approved account + a game page
with no visitors earns $0. The house-ad strip is the reliable earner
here: it converts game players into product buyers regardless of
AdSense status. See [ADS-SETUP.md](ADS-SETUP.md) for the Blogger embed
steps and the slot-ID walkthrough.

## License

MIT — see [LICENSE](LICENSE). Free to play, fork, and build on.

## Author

Syed Shahid / Syed Ventures
