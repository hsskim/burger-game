# 🍔 Burger Game

**Eat in order, stack up your burger.**

A grid-based path puzzle where you play as a two-bun burger character. Move around a kitchen, eat ingredients **in the exact order** on your order sheet, and finish the burger before the timer runs out — while dodging the trash scattered across the floor.

Built as a single HTML file with **no frameworks, no build step, and no image assets**. Just open it and play.

🔗 **[Play Burger Game](https://hsskim.github.io/burger-game/)**

> 🖥️ **Keyboard only.** The game is played with the arrow keys or WASD, so it needs a desktop or laptop. Mobile visitors get a friendly notice instead of a broken screen.

---

## 🎮 How to Play

Your goal is to build the burger on the order sheet. Step onto an ingredient and you eat it **immediately** — there is no undo, so plan your route before you move.

### Controls

| Key | Action |
|---|---|
| `←` `↑` `↓` `→` or `WASD` | Move |
| `Enter` | Start Stage Mode · confirm · next stage/round |
| `Space` | Start Endless Mode |
| `R` | Restart the current stage *(Stage Mode only)* |
| `ESC` | Back out, or cancel a popup |

### Scoring

| Rating | Condition |
|---|---|
| ⭐ | Finish the burger before time runs out |
| ⭐⭐ | Finish it **and** either avoid all trash **or** get the order exactly right |
| ⭐⭐⭐ | Finish it, eat no trash, **and** follow the order perfectly |

Eating **3 pieces of trash** ruins the burger and ends the run. There are 8 ingredients (🥩 🧀 🥬 🍅 🧅 🥓 🍳 🥒) and 5 kinds of trash (🧦 🧼 👟 🧽 🎱) — each ingredient appears exactly once per map, so there is no spare.

---

## 🗺️ Two Modes

### Stage Mode

**10 handcrafted stages** that open up as you clear them. Your best rating per stage is saved.

| Stages | Map | Recipe |
|---|---|---|
| 1–5 | 9×9 | 2 → 7 ingredients |
| 6–9 | 11×11 | 5 → 7 ingredients |
| 10 | 13×13 | all 8 ingredients |

Every stage runs on a 15-second timer. The difficulty comes from map size, route length, and how tightly the trash blocks the shortcuts.

### Endless Mode

Procedurally generated maps, round after round, with **3 lives**.

- Fail a round and you lose a life — the same map comes back so you can retry it.
- A flawless 3-star clear restores one life (up to 3).
- Lose all three and the run ends. Your best round and its average star rating are saved.

Difficulty climbs until round 15, then deliberately flattens out — there are only 8 ingredients, so that is the natural ceiling. From there it becomes an endurance run.

| Rounds | Map | Ingredients | Timer |
|---|---|---|---|
| 1–5 | 9×9 | 2 → 4 | 10s |
| 6–14 | 11×11 | 5 → 8 | 15s |
| 15+ | 13×13 | 8 | 20s |

---

## ✨ Features

**🌐 Korean & English** — The language is picked automatically from your browser's preferences (the full ordered list, not just the top entry), and you can switch it from the title or stage select screen. Your choice is remembered.

**🧩 Every map is guaranteed solvable** — A BFS solver checks that a real 3-star route exists: eat everything in the right order, touching no trash and no ingredient that isn't next in line. Handcrafted stages are verified at startup; generated maps are verified before they ever reach you. A separate check catches data typos the solver can't see, like a grid row one character short.

**🎯 Generated maps that respect your time** — Endless Mode builds several candidate maps per round and keeps the one that forces the least backtracking. Ingredients are never placed in dead ends, and trash is laid on the shortcut so the safe route has to go around it — active avoidance, not random noise.

**💾 Progress that persists** — Stage ratings, endless records, onboarding, and language all live in `localStorage`. If storage is blocked (private browsing, strict cookie settings), the game degrades quietly instead of breaking.

**🎨 Hand-drawn feel, zero assets** — Every graphic is an inline SVG string. The burger smiles and puffs up when it eats something good, frowns when it eats trash, and the screen shakes. Movement is interpolated and popups bounce in.

---

## 🚀 Running Locally

No build, no dependencies, no install.

```bash
open index.html
```

Double-clicking the file works too. A local server is optional — it only smooths out web font loading:

```bash
python3 -m http.server
```

Works in any modern browser (Chrome, Edge, Safari, Firefox).

---

## 🛠️ How It's Built

Everything lives in one `index.html`: markup, styles, game logic, and SVG art as template strings. No npm, no bundler, no CDN scripts — the only external resource is the Pretendard web font, which falls back to a system sans-serif offline.

| Concern | Where |
|---|---|
| Stage data, difficulty curve, strings | Constant tables at the top of the file |
| Solver | `validateStage` / `bfsDist` — BFS over the parsed grid |
| Map generator | `generateStage` / `buildEndlessMap` — recursive-backtracker maze, braided, then verified |
| Localization | `STRINGS` dictionary + `t()`; DOM side handled by `applyLanguage()` |
| Rendering | Canvas, split per screen (`renderTitle` / `renderSelect` / `renderPlay`) |

Adding a stage means adding one entry to the `STAGES` array — the solver will tell you at startup if it isn't fair.

Development notes and design decisions live in [CLAUDE.md](CLAUDE.md) and [plan.md](plan.md); the original game design is in [prd.md](prd.md).

---

## 📄 License

© 2026 hsskim. All rights reserved.

This repository is public for reading and reference, but no license is granted for reuse or redistribution.
