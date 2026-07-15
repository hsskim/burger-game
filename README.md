# 🍔 Burger Game v2

**Burger Game** is a 2D arcade puzzle game where you move a cute two-bun burger character around a grid, eating ingredients in the exact order on your order sheet to build the perfect burger before time runs out — all while dodging trash traps. Built purely with HTML5 Canvas and JavaScript (no frameworks, no image files — SVG only), it runs instantly in any browser.

🔗 **DEMO:** [Play Burger Game](https://hsskim.github.io/burger-game/)

> 🖥️ **PC (keyboard) only.** The game is played with the arrow keys / WASD.

---

## 🆕 What's New in v2

- **10 handcrafted stages** (up from 5), growing from 9×9 up to 13×13 maps.
- **Endless Mode:** procedurally generated random maps, round after round. Start with **3 lives** — lose one on each failure, restore one with a flawless 3-star clear, and the run ends when they're gone. Your best round and average star rating are saved.
- **Solver-guaranteed maps:** every stage and every generated map is verified by a BFS solver to have a real 3-star (correct-order, trap-free) path — no impossible layouts.
- **Onboarding popups** the first time you enter each mode.

---

## 🎮 How to Play

1. **Movement:** Use the arrow keys (`←`, `↑`, `↓`, `→`) or `WASD` to move your cute burger character around the grid.
2. **Controls:**
   - `Enter`: Start Stage Mode (from the title) / proceed to the next stage / confirm popup
   - `Space`: Start Endless Mode (from the title)
   - `R`: Instantly restart the current stage (Stage Mode only)
   - `ESC`: Pause, go back, or cancel a popup

---

## 🎯 Your Mission

Your ultimate goal is to build the perfect burger! Navigate the kitchen, grab what you need, and deliver the order to your hungry customers.

- **Beat the Clock:** Gather all the required ingredients on your order list before the timer runs out.
- **Watch Your Step:** The kitchen is messy! If you accidentally eat 3 pieces of trash (like socks or soap), your burger is ruined and it's game over.
- **Aim for Perfection:** Can you get a 3-star rating?
  - ⭐ **1 Star:** Complete the burger in time.
  - ⭐⭐ **2 Stars:** Complete it while either avoiding all traps OR getting the exact ingredient order right.
  - ⭐⭐⭐ **3 Stars:** Flawless victory! No traps eaten AND perfect ingredient order.

---

## 🎨 Features

* **Dynamic UI & Animations:**
  * Detailed visual feedback: The burger smiles and swells up (`charYum`) when eating delicious ingredients, but the screen shakes and it frowns (`charSad`) when eating trash.
  * The results screen title changes dynamically based on your star rating ("Just finished.. 😅", "Burger Complete! 🎉", "Perfect Burger ✨").
  * Enjoy smooth grid movement (Lerp) and bouncy animations (Ease-out-back) rendered directly on the Canvas.
* **Local Save Support:**
  * Uses `localStorage` to permanently save your unlocked stages and the highest star rating achieved for each.
* **Design System:**
  * A warm, pastel color palette paired with clean outer shadows and rounded panel borders provides a visually rich and charming aesthetic.

---

## 🚀 Setup

This game does not require any build steps or dependency installations.
1. Simply double-click `index.html` to open it in any modern web browser (Chrome, Edge, Safari, etc.).
2. For the best experience (smooth font loading and rendering), it is recommended to run it via a local server (e.g., VS Code Live Server, `python -m http.server`, `npx serve`, etc.).

Enjoy building the perfect burger! 🍔
