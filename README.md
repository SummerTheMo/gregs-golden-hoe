# 🕷️ Greg's Golden Hoe

A retro 8-bit arcade game featuring Greg the friendly brown recluse spider on a quest to find the legendary Golden Hoe!

![Game Preview](https://img.shields.io/badge/Status-Playable-brightgreen) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)

---

## 🎮 Play the Game

Simply open `index.html` in any modern web browser — no build process, no dependencies, no installation required!

```bash
# Clone and play
git clone https://github.com/SummerTheMo/gregs-golden-hoe.git
cd gregs-golden-hoe
open index.html  # macOS
# or: start index.html  # Windows
# or: xdg-open index.html  # Linux
```

---

## 📖 Story

Help **Greg**, a friendly brown recluse spider, explore an 8-inch × 8-inch dirt plot in search of the legendary **Golden Hoe**. Dig through the soil, discover hidden treasures, and celebrate when you finally unearth the prize!

---

## 🕹️ Controls

### Desktop
| Action | Control |
|--------|---------|
| Move Up | `↑` Arrow Key |
| Move Down | `↓` Arrow Key |
| Move Left | `←` Arrow Key |
| Move Right | `→` Arrow Key |
| Dig | `Spacebar` or `Click` on Greg's current square |

### Mobile (Touch Devices)
- **D-Pad** — Virtual directional pad appears on touch screens
- **DIG Button** — Center button to dig at current position

---

## ✨ Features

### Gameplay
- **8×8 Grid** — 64 individual squares to explore
- **Strategic Digging** — Each square can only be dug once
- **10% Chance** — Golden hoe has a 1-in-10 probability per dig
- **Hidden Treasures** — Discover tools and vegetables along the way

### Inventory System
- **Inventory Bar** — Displays above the game grid
- **Item Found Overlay** — When you discover an item:
  - Semi-transparent background appears
  - Item displayed at 4× size with glowing gold outline
  - "Item Found!" title with item name
- **Fly-to-Inventory Animation** — After 3 seconds, item scales and pans into inventory

### Hidden Items
| Tools | Vegetables |
|-------|------------|
| 🔧 Rake | 🥕 Carrot |
| ⛏️ Shovel | 🥔 Potato |
| 🔱 Pitchfork | 🍅 Tomato |
| 🪓 Chisel | 🥬 Lettuce |
| 🎣 Broken Fishing Rod | 🧅 Onion |

### Visual Design
- **Retro 8-Bit Aesthetic** — Pixel-art sprites and limited color palette
- **Animated Sprites** — Greg dances when the golden hoe is found!
- **Particle Effects** — Satisfying dig animations
- **Shimmer Effect** — Golden hoe glows with importance

### Game States
1. **Playing** — Explore and dig freely
2. **Showing Item** — 3-second item discovery overlay
3. **Celebrating** — 15-second victory dance with confetti
4. **Won** — View your collected items and play again

---

## 🐛 Support Bug Conservation

When you win, you'll have the option to **donate to entomology and bug conservation works**! Help protect the amazing insects and arachnids that inspire games like this.

---

## 🏗️ Technical Details

### Architecture
- **Single HTML File** — Complete game in one file (~55KB)
- **No External Dependencies** — Pure HTML5, CSS3, and ES6+ JavaScript
- **SVG Sprites** — Scalable pixel-art graphics rendered inline
- **requestAnimationFrame** — Smooth 60 FPS game loop
- **Centralized State** — Predictable game state management

### Browser Compatibility
- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Opera

---

## 📁 Project Structure

```
gregs-golden-hoe/
├── index.html                         # Complete game (HTML + CSS + JavaScript)
├── README.md                          # This file
├── .gitignore                         # Standard gitignore
└── .github/workflows/static.yaml      # GitHub Pages deployment workflow
```

---

## 🎯 Game Objective

1. Move Greg around the 8×8 grid using arrow keys (or d-pad on mobile)
2. Press spacebar or click to dig at Greg's current position
3. Collect items in your inventory
4. Keep digging until you find the **Golden Hoe**!
5. Celebrate your victory! 🎉

---

## 🛠️ Development

Want to modify the game? Key constants are at the top of the JavaScript section:

```javascript
const GRID_SIZE = 8;                  // Grid dimensions
const GOLDEN_HOE_CHANCE = 0.10;       // 10% per dig
const CELEBRATION_DURATION = 15000;   // 15 seconds
const ITEM_DISPLAY_DURATION = 3000;   // Item overlay time
const ITEM_FLY_DURATION = 800;        // Fly animation time
```

---

## 📊 Google Analytics Setup

This site uses Google Analytics 4 for tracking. The GA Measurement ID is injected during deployment via GitHub Actions.

### Setup Steps:

1. Go to your repository **Settings → Secrets and variables → Actions**
2. Add a new **Repository secret** named `GA_MEASUREMENT_ID`
3. Set the value to your GA4 Measurement ID (e.g., `G-XXXXXXXXXX`)

The `static.yaml` workflow will automatically replace the placeholder `__GA_MEASUREMENT_ID__` in `index.html` during deployment.

> **Note**: If the secret is not set, analytics will be disabled but the site will still work normally.

---

## �📜 License

This project is open source and available for personal and educational use.

---

## 🙏 Credits

Created with ❤️ featuring Greg the friendly brown recluse spider.

---

**Happy digging!** 🏆✨

