# 🎠 WonderPlay — Learn & Play

A colourful, mobile-first learning game for young children. Five mini-games in one
self-contained HTML file — no build step, no dependencies, no install.

**▶️ Deploy to Vercel in one click:**
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/hamzav888/shapesgamedemo)

Installs to your phone's home screen and **plays fully offline**.

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

## 🚀 Deploying

### Vercel (recommended)

The repo is deploy-ready — no build step, no environment variables.

**One click:** use the Deploy button above, or

**From the dashboard:** [vercel.com/new](https://vercel.com/new) → import
`hamzav888/shapesgamedemo` → **Deploy**. Leave every setting on its default;
Vercel serves it as a static site and `vercel.json` handles the rest.

**From the CLI:**

```bash
npm i -g vercel && vercel --prod
```

### Install it on your phone

Once deployed, open the URL on your phone:

- **iOS** — Share → *Add to Home Screen*
- **Android** — tap the green **Add to Home Screen** banner in the app, or the browser's *Install* prompt

It then launches full-screen with no browser chrome, and works with no
signal at all.

### Running locally

Open `index.html` directly in any browser. (The service worker and manifest
need a real server, so for the full PWA experience run
`python -m http.server 8000` and visit `http://localhost:8000`.)

## 📦 Progressive Web App

- **`manifest.webmanifest`** — standalone display, maskable icons, and app shortcuts
  that jump straight to Balloon Pop or the Sticker Book
- **`sw.js`** — offline-first service worker. Network-first for navigations (so
  updates land immediately), cache-first for assets, stale-while-revalidate for fonts
- **`vercel.json`** — long-lived immutable caching for icons, always-revalidate for
  `index.html` and `sw.js`, correct `Content-Type` for the manifest, plus
  `nosniff` / `Referrer-Policy` / `Permissions-Policy` headers
- **`icons/`** — six PNGs including Android **maskable** variants

## 🗂️ Structure

```
index.html            the entire game (~1,850 lines)
manifest.webmanifest  PWA metadata
sw.js                 offline service worker
vercel.json           hosting config: headers + caching
icons/                app icons (192/512, maskable, apple-touch, favicon)
```

## 🛠️ Tech

Vanilla HTML/CSS/JS in a single file — no frameworks, no build tooling, no
dependencies. All artwork is inline SVG, all sound is synthesised at runtime via
the Web Audio API, and app icons are generated as raw PNGs. The only external
request is a Google Font, which is cached for offline use.
