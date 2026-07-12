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

## 📋 Core Rules & System

### 1. Stage Clear
- You have a **20-second time limit**. To clear a stage, you must collect **all the ingredients** listed in the **[Order]** panel on the left at least once.
- Even if you eat the ingredients in the wrong order or accidentally consume garbage (traps), the stage is cleared as long as you gather all the required ingredients before time runs out.

### 2. Game Over
If either of the following two conditions is met, it results in an immediate failure:
- ⏰ **Time Over:** Failed to collect all required ingredients before the timer reaches 0.
- 😥 **Poor Hygiene (3-Strike):** Eaten scattered **traps (socks, soap, shoes, etc.)** a total of **3 times**.

### 3. ⭐ Star Rating System (Max 3 Stars)
Upon clearing a stage, you earn stars independently based on the objectives you achieve. This encourages players to try for secondary objectives even if they make a mistake.
- **Base Star (★ 1):** Successfully clear the stage (guaranteed).
- **Hygiene Bonus (+★ 1):** Clear the stage **without eating a single trap**.
- **Accuracy Bonus (+★ 1):** Collect the ingredients in the **exact order** shown on the recipe.
> 💡 *Example: Even if you accidentally step on 1 trap, you can still earn a total of 2 stars if your ingredient order is perfectly accurate!*

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
