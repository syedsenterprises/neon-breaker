# Neon Breaker — Ads Setup Guide

The ad-enabled game is `neon-breaker-ads.html`: the exact same game as
`neon-breaker.html` (script verified byte-identical) with two AdSense
units — one above, one below the game — plus a house-ad strip promoting
Syed Ventures' own products. Nothing is published by this guide; follow
the steps to go live yourself.

## 1. Get your real AdSense slot IDs

1. Sign in to AdSense (account `pub-7363635746119645`, the Estate Path
   account).
2. Go to **Ads → By ad unit → Display ads → Create a display ad unit**.
3. Create **two** units (one will go above the game, one below it).
   Responsive size is fine for both.
4. Copy each unit's numeric **Ad slot ID** (it looks like `1234567890`).

## 2. Put the slot IDs into the file

Open `neon-breaker-ads.html` in any text editor and find the two
placeholders (each is marked with a `TODO` comment right above it):

```html
data-ad-slot="0000000000"
```

Replace `0000000000` with your real slot ID — once for the **above-game**
unit, once for the **below-game** unit. They can be the same ID or two
different ones; two different ones gives cleaner reporting.

Do not touch anything else in the file. In particular, do not move the
ad units: they must stay outside the `#wrap` game container.

## 3. Embed it on Blogger (Estate Path or any Blogger blog)

`neon-breaker-ads.html` is a single self-contained file, so it pastes
straight into a Blogger page:

1. In Blogger, go to **Pages → New page**.
2. Give it a title, e.g. **"Neon Breaker — Play Free"**.
3. Switch the editor to **HTML view** (the pencil icon → "HTML view").
4. Paste the **entire contents** of `neon-breaker-ads.html`.
5. Switch back to preview to check the game loads, then **Publish**.
6. Open the live page and confirm: game plays, top ad slot sits above
   the game, bottom ad slot + house-ad strip sit below it, nothing
   covers the canvas or the pause/mute buttons.

Notes:

- The page needs your AdSense `ads.txt` live on the domain for ads to
  serve (Estate Path already has `pub-7363635746119645` in its ads.txt).
- If ads show blank at first, that is normal: the account must be fully
  approved and the page must be crawled before units fill. The house-ad
  strip still shows and still links to the products either way.
- Do **not** paste the file into a blog *post* with the compose editor
  in normal view — it will mangle the code. HTML view only.

## 4. AdSense policy rules (do not break these)

These rules are already baked into the layout — keep them that way:

- **No ads over gameplay.** The units sit above and below the game
  container only. Never position an ad over the canvas, the HUD buttons,
  or the controls.
- **No click incentives.** Never write "click the ad", "support us by
  clicking", or gate a life/level/continue behind an ad click.
- **No disguised ads.** The house-ad strip is labelled "From Syed
  Ventures" and is visually distinct from the Google units — never make
  it look like a Google ad.
- **Auto ads: keep OFF for this page** until the two manual slots are
  verified live. Auto ads can place units anywhere, including over
  gameplay. (The file's AdSense loader script already covers manual
  units; auto ads is a dashboard switch, not a second script tag.)

## 5. What to expect (honest version)

- **AdSense revenue:** $0 until the account is fully approved *and* the
  page gets real traffic. Game pages earn low RPMs (a few dollars per
  1,000 views at best) — this is a slow trickle, not a windfall.
- **House-ad revenue:** the reliable channel. Every player sees the
  Practice Pack ($14.99), Math Workbook ($9.99), and Cheat Sheets
  ($7.99) links whether or not AdSense fills. One $7.99 sale beats
  thousands of ad impressions.
- **Best next step after publishing:** link the game page from the
  Estate Path homepage and from the GitHub repo README, so the game
  actually gets players.
