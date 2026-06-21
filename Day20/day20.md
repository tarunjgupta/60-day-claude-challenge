# Day 20 – #60DayClaudeChallenge
## 🧩 Face Puzzle Game — Snap, Scramble, Solve!

---

## What I Did Today

On Day 20, I built a **Face Puzzle Game** — a complete, self-contained single HTML file application that uses your webcam to capture a photo of your face, slices it into a grid of puzzle pieces, scrambles them, and challenges you to solve it as fast as possible.

**Task:** Build a fully working face puzzle game with camera access, puzzle generation, drag-and-drop controls, timer, move counter, win detection, and a persistent leaderboard — all in one HTML file with zero external framework dependencies.

---

## Features Implemented

| Feature | Description |
|---|---|
| 📷 Camera Access | Requests webcam permission, shows live preview with face guide overlay |
| 📸 Photo Capture | Snapshot button captures and crops a square photo of your face |
| 🧩 Puzzle Generation | Choose 3×3 (Easy), 4×4 (Medium), or 5×5 (Hard) grid difficulty |
| 🔀 Solvable Scramble | Pieces are randomly scrambled with guaranteed solvability (even inversions) |
| 🖱️ Drag & Drop | Full mouse drag support for desktop with piece swapping |
| 📱 Touch Gestures | Touch drag support for mobile and tablet devices |
| ⏱️ Live Timer | Real-time timer in mm:ss.t format, starts on puzzle begin |
| 👆 Move Counter | Tracks total number of piece swaps made |
| ✅ Correct Tracker | Shows how many pieces are in their correct position |
| 🟢 Visual Feedback | Green border on correctly placed pieces, purple glow while dragging |
| 🎉 Win Detection | Automatically detects when all pieces are correctly placed |
| 🏆 Leaderboard | Top 5 best times saved to localStorage with date, moves, and difficulty |
| 🎊 Confetti | Celebration confetti animation on puzzle completion |
| 🔄 Replay Options | Retake Photo, Play Again, and New Photo buttons throughout |
| 🎨 Modern UI | Glassmorphism design, gradient accents, smooth animations, dark theme |
| 📐 Responsive | Works on desktop, tablet, and mobile screens |

---

## Technical Highlights

### Solvability Guarantee
The puzzle uses **inversion counting** to ensure every generated scramble is solvable. For a standard sliding puzzle without a blank tile (swap-based), the number of inversions must be even for the puzzle to be solvable back to the original arrangement.

### Image Slicing
The captured photo is drawn to a canvas, then each puzzle piece uses `background-image` with calculated `background-position` offsets to display only its portion of the full image — no actual image slicing needed.

### Drag System
A unified pointer system handles both `mouse` and `touch` events. Pieces snap to the nearest grid cell on release and swap positions with whatever piece occupies the target cell.

### Camera Handling
- Uses `getUserMedia()` with `facingMode: "user"` for front-facing camera
- Mirrors the video feed for natural selfie experience
- Gracefully handles permission denied with user-friendly error message
- Crops to square aspect ratio from center of frame

---

## Key Learnings

1. **Canvas Image Manipulation** — Using canvas `drawImage()` with source/destination rectangles enables precise cropping and mirroring of camera frames without any image processing library.

2. **Puzzle Solvability Math** — Not all random permutations are solvable. Understanding parity and inversion counting is essential to guarantee the player can actually complete the puzzle.

3. **Unified Touch & Mouse Handling** — Building a single drag system that works across desktop and mobile requires careful event handling, `preventDefault()` on touch events, and coordinate normalization.

4. **CSS Background Tricks** — Using `background-image` + `background-position` + `background-size` on each piece is far more efficient than creating separate canvas/image elements for each tile.

5. **localStorage Persistence** — Simple JSON serialization to localStorage creates a persistent leaderboard across sessions with zero backend infrastructure.

---

## Tools & Stack

- **Claude** — Generated the complete single-file HTML application
- **Technologies:** Vanilla HTML5, CSS3, JavaScript (ES6+)
- **APIs Used:** `getUserMedia()`, Canvas API, `localStorage`
- **Design:** Glassmorphism, CSS gradients, keyframe animations, responsive layout
- **External Dependencies:** Google Fonts (Inter, Outfit) only

---

## Files in This Folder

| File | Description |
|---|---|
| `day20.md` | This file — task overview, features, and learnings |
| `Day20.html` | Complete Face Puzzle Game — single self-contained HTML file |

---

## How to Play

1. Open `Day20.html` in your browser (Chrome, Firefox, or Safari)
2. Allow camera access when prompted
3. Position your face in the guide circle and click **Take Photo**
4. Choose your difficulty: **3×3**, **4×4**, or **5×5**
5. Drag pieces to swap them and reconstruct your face
6. Beat your best time and climb the leaderboard! 🏆

---

## Connect & Follow the Challenge

- 🔗 GitHub: [#60DayClaudeChallenge Repository](https://github.com/tarunjgupta/60-day-claude-challenge)
- 💼 LinkedIn: Follow along for daily posts
- 🏷️ Hashtags: `#60DayClaudeChallenge` `#Claude` `#Anthropic` `#AIProductivity` `#WebDev`

---

*Day 20 of 60 — Turning selfies into puzzles, one pixel at a time.* 🧩
