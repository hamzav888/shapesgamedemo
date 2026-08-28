# 🎠 WonderPlay — Learn & Play

A colourful, mobile-first learning game for young children. Five mini-games in one
self-contained HTML file — no build step, no dependencies, no install.

**▶️ [Play it here](https://hamzav888.github.io/shapesgamedemo/)** *(enable GitHub Pages to activate)*

---

## 🎮 The five games

| Game | What it teaches | Modes |
|------|-----------------|-------|
| 🔷 **Shapes** | Shape recognition & names | **Match** (drag shapes onto outlines) · **Tap It** (find the named shape) · **Find All** (spot every match in a grid) |
| 🔢 **Numbers** | Counting to 10 | **Count It** (tap objects to count, then pick the number) · **In Order** (tap 1→10 in sequence) |
| 🎨 **Colours** | Colour names & creativity | **Learn** (10 spoken colours) · **Paint** (5 fill-in pictures, 12 colours + magic rainbow brush) |
| 🧩 **Puzzles** | Spatial reasoning | 6 hand-drawn scenes at Easy (4 pieces) · Medium (6) · Hard (8) |
| 🎈 **Balloon Pop** | Reflexes & reward | Endless popping with combo streaks and **rare golden balloons** that drop collectible stickers |

## ✨ Features

- **📖 Sticker Book** — 12 collectible stickers hidden in rare golden balloons, saved between sessions
- **⭐ Star economy** — earn stars in every game; progress badges and 🏆 trophies appear on the home screen
- **🔊 Sound & speech** — procedural WebAudio effects (no audio files) plus spoken prompts for pre-readers
- **📳 Haptics** — vibration feedback on supported devices
- **❌ Clear wrong-answer feedback** — red screen flare, ring, shake, buzzer and a friendly hint toast; progress never advances on a wrong tap
- **💾 Saves automatically** — stars, stickers and progress persist in `localStorage`

## 📱 Mobile first

Built as an app shell rather than a web page:

- Fixed `100dvh` layout — the header stays put, only the content scrolls
- Safe-area insets for notched phones; no overscroll bounce or pull-to-refresh
- Every screen fits without scrolling in portrait **and** landscape
- All tap targets meet the 44px accessibility minimum
- Add to Home Screen supported (iOS & Android) for a full-screen, app-like experience
- Respects `prefers-reduced-motion`

## 🚀 Running it

Just open `index.html` in any modern browser — that's it.

To play on your phone, enable GitHub Pages:
**Settings → Pages → Source: `main` branch, `/root`** — then open the URL and
tap *Share → Add to Home Screen*.

## 🛠️ Tech

Single `index.html` (~1,800 lines). Vanilla HTML/CSS/JS — no frameworks, no build
tooling, no external assets beyond a Google Font. All artwork is inline SVG, all
sound is synthesised at runtime via the Web Audio API.
