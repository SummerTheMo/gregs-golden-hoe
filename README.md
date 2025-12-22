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

| Action | Control |
|--------|---------|
| Move Up | `↑` Arrow Key |
| Move Down | `↓` Arrow Key |
| Move Left | `←` Arrow Key |
| Move Right | `→` Arrow Key |
| Dig | `Click` on Greg's current square |

---

## ✨ Features

### Gameplay
- **8×8 Grid** — 64 individual squares to explore
- **Strategic Digging** — Each square can only be dug once
- **10% Chance** — Golden hoe has a 1-in-10 probability per dig
- **Hidden Treasures** — Discover tools and vegetables along the way

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
2. **Celebrating** — 15-second victory dance with confetti
3. **Won** — View your stats and play again

---

## 🏗️ Technical Details

### Architecture
- **Single HTML File** — Complete game in one file (~45KB)
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
├── index.html    # Complete game (HTML + CSS + JavaScript)
└── README.md     # This file
```

---

## 🎯 Game Objective

1. Move Greg around the 8×8 grid using arrow keys
2. Click to dig at Greg's current position
3. Find hidden items to increase your score
4. Keep digging until you find the **Golden Hoe**!
5. Celebrate your victory! 🎉

---

## 📊 Stats Tracked

- **Position** — Greg's current coordinates
- **Digs** — Total squares excavated
- **Items Found** — Treasures discovered
- **Remaining** — Undug squares left

---

## 🛠️ Development

Want to modify the game? Key constants are at the top of the JavaScript section:

```javascript
const GRID_SIZE = 8;              // Grid dimensions
const GOLDEN_HOE_CHANCE = 0.10;   // 10% per dig
const CELEBRATION_DURATION = 15000; // 15 seconds
const MOVE_COOLDOWN = 100;        // Prevent spam
```

---

## 📜 License

This project is open source and available for personal and educational use.

---

## 🙏 Credits

Created with ❤️ featuring Greg the friendly brown recluse spider.

---

**Happy digging!** 🏆✨
