# Focus Reset

A browser-based brain-training mini-game suite — **8 quick focus games** plus a **real-time 2-player race mode**. Shipped as a single, self-contained HTML file: no build step, no framework, no backend.

**▶ Live demo:** https://YOUR-USERNAME.github.io/YOUR-REPO/

---

## Overview

Focus Reset turns short, focused attention drills into a fast, playful routine that runs entirely in the browser — no install, no sign-up. Every game starts on **Easy** and steps up to **Medium** and **Hard** on its own as you play, so a session adapts to the player rather than the other way around.

The app has two modes:

- **Solo** — play the 8 games back-to-back, with a day streak, personal bests and a daily challenge.
- **Dost mode (2-player race)** — two players connect directly and race through all 8 games on an identical, randomly ordered sequence, with a live scorecard.

## Features

- **8 mini-games** covering working memory, attention, inhibition and processing speed.
- **Adaptive difficulty** — Easy → Medium → Hard inside every game.
- **Live 2-player race** over WebRTC (PeerJS): create or join with a 5-character room code — no accounts, no server.
- **Progress tracking** — day streak, games played, personal bests and a "reached Hard" counter, saved locally.
- **Built-in audio** — every sound effect and the ambient music are generated with the Web Audio API (no audio files).
- **Responsive, mobile-first** — light and dark themes, safe-area aware, designed to fit a single screen.
- **Works offline** for solo play.

## The games

| # | Game | Trains |
|---|------|--------|
| 1 | Yaad Rakho | Working memory — repeat a growing sequence of pads |
| 2 | Sirf Hara Pakdo | Sustained attention — tap the green, ignore the red distractors |
| 3 | Number Yaad Karo | Short-term memory — recall and type a number |
| 4 | Rang Pehchano | Inhibition — pick the ink colour, not the word |
| 5 | Alag Kaun? | Visual scanning — find the odd character |
| 6 | Jodi Milao | Visual memory — match the card pairs |
| 7 | Dimaag Garam | Processing speed — rapid mental arithmetic |
| 8 | Jaldi Dabao | Reaction & impulse control — tap on green, hold on red |

## Dost mode (2-player race)

1. One player taps **"Code banao"** to generate a 5-character code (or **Copy** it).
2. The other taps **"Code daalo"**, enters the code and presses **Enter** (or **"Let's go"**).
3. Both players play the same 8 games in the same random order — roughly 35–40 seconds each, about 5 minutes for a full match.
4. A scorecard tracks each game (win / loss / draw) with a progress bar for the whole match.
5. If a player drops out, the other sees **"Dost chala gaya"** after a 5-second grace period.

The connection is peer-to-peer: peers are introduced through the free PeerJS broker, and game data then travels directly between the two browsers.

## Tech

- **Vanilla JavaScript + HTML + CSS** — a single `index.html`, no framework and no bundler.
- **WebRTC (via PeerJS)** for real-time multiplayer presence and results.
- **Web Audio API** for all sound.
- **localStorage** for progress.
- **GitHub Pages** for hosting.

## Run it locally

No tooling required:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
cd YOUR-REPO
# then open index.html in a browser
```

Solo mode works offline; multiplayer needs an internet connection (for the PeerJS signalling broker).

## Deploy to GitHub Pages

1. Rename the game file to **`index.html`** so it loads at the site root.
2. Push the repository (see the steps below).
3. In the repository: **Settings → Pages → Source: Deploy from a branch → `main` / `root` → Save**.
4. The game goes live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`.

```bash
# first-time push
git init
git add index.html README.md
git commit -m "Initial commit: Focus Reset"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

## Project structure

```
.
├── index.html     # the entire app — markup, styles, logic and multiplayer
└── README.md
```

## Notes & limitations

- Multiplayer uses a public PeerJS broker; some corporate or school networks block WebRTC.
- This is a focus-practice tool, **not** a medical treatment or a diagnostic device.

## License

© 2026 Stan. All rights reserved.
