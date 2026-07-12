# 🍔 Burger Game v1

**Burger Game v1** is a 2D arcade puzzle game where you must collect ingredients to build the perfect burger within a time limit while dodging traps. Built purely with HTML5 Canvas and JavaScript, it requires no external frameworks or image assets (using SVG instead) and runs instantly in your browser.

---

## 🎮 How to Play

1. **Movement:** Use the arrow keys (`←`, `↑`, `↓`, `→`) or `WASD` to move your cute burger character around the grid.
2. **Controls:**
   - `Enter` / `Space`: Start game, proceed to the next stage, confirm popup
   - `R`: Instantly restart the current stage
   - `ESC`: Pause game, return to stage selection, cancel popup

---

## 🎯 Your Mission

Your ultimate goal is to build the perfect burger! Navigate the kitchen, grab what you need, and deliver the order to your hungry customers.

- **Beat the Clock:** Gather all the required ingredients on your order list before the 20-second timer runs out.
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
