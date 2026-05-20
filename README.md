# 🌟 Feelings Friends
### Emotional Check-in Tool for Ages 1–5

> A touch-friendly, read-free emotional check-in experience designed for toddlers and young children in daycares, hospitals, preschools, and therapeutic settings.

---

## 📖 Overview

**Feelings Friends** is a single-file, browser-based emotional check-in tool built specifically for children aged 1–5 who cannot yet read. It uses illustrated cartoon faces, vibrant colors, and large touch targets to guide young children through identifying and expressing how they feel — no adult assistance required for the core interaction.

The tool includes a built-in **Caregiver Dashboard** that tracks up to 20 children's daily emotional check-ins across a full week, giving teachers, nurses, and therapists a quick visual overview of emotional patterns in their group.

---

## ✨ Features

### For Children
- **Colorful name keyboard** — large, color-coded letter buttons that pop in one at a time; no reading required
- **Illustrated emotion faces** — six hand-drawn SVG cartoon characters with expressive animations representing Happy, Sad, Angry, Scared, Surprised, and Calm
- **Color picker** — 12 vivid color swatches; the child chooses the color that *feels like* their emotion
- **Sticker canvas** — tap a sticker from the tray, tap the canvas to place it; full-color emoji rendered via offscreen canvas
- **Celebratory done screen** — confetti, floating stars, and a warm, age-appropriate message tied to their emotion

### For Caregivers
- **Weekly dashboard** — tracks all 20 children across Mon–Sun in a color-coded grid
- **Today's column highlighted** — gold outline and ★ marker for the current day
- **Emotion + color dot** per cell — instant visual summary at a glance
- **Hover tooltips** (desktop) — shows child name, day, and emotion on hover
- **Stats row** — check-in count, most common emotion today, current day
- **Clear today** — two-tap confirmation to reset the current day's entries
- **Demo data** — auto-seeded on first load with realistic sample data for all 20 roster children
- **Persistent storage** — all check-ins saved to `localStorage`, survive page refresh

---

## 🧠 Design Principles

| Principle | Implementation |
|-----------|---------------|
| **No reading required** | All emotion identification is done via illustrated faces and color |
| **Large touch targets** | All interactive elements sized for small fingers on tablets |
| **Minimal steps** | Four screens: Name → Emotion → Color → Stickers |
| **Emotionally safe** | Each completion screen delivers a gentle, validating message |
| **Caregiver visibility** | Dashboard gives staff a quick overview without interrupting the child's flow |
| **Privacy by design** | No data leaves the device; all storage is local |

---

## 🎭 Emotions Supported

| Emotion | Color | Face Characteristics |
|---------|-------|---------------------|
| 😊 Happy | Yellow `#FFD93D` | Wide smile, rosy cheeks |
| 😢 Sad | Blue `#74B3CE` | Downturned brows, tears |
| 😠 Angry | Red `#FF6B6B` | Furrowed brows, steam lines |
| 😨 Scared | Purple `#B084CC` | Wide eyes, open mouth |
| 😲 Surprised | Orange `#FF9F43` | Raised brows, O-shaped mouth |
| 😌 Calm | Green `#6BCB77` | Soft closed eyes, small smile |

---

## 🚀 Getting Started

### Requirements
- Any modern browser (Chrome, Safari, Firefox, Edge)
- No server, build tools, or dependencies required
- Works offline after first load (no server calls after Google Fonts)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/feelings-friends.git

# Navigate into the project
cd feelings-friends

# Open directly in your browser
open feelings-friends.html
```

Or simply **download `feelings-friends.html`** and open it in any browser. That's it.

---

## 📱 Recommended Usage

| Setting | Device | Orientation |
|---------|--------|-------------|
| Daycare / Preschool | iPad or Android tablet | Portrait |
| Hospital pediatric ward | Tablet mounted at child level | Portrait |
| School counselor's office | iPad or laptop | Either |
| Telehealth session | Shared screen or child's device | Portrait |

**Tip for caregivers:** Open the tool in full-screen mode on a tablet (tap the share icon → "Add to Home Screen" on iOS) for the best experience. The child sees the check-in flow; you access the dashboard via the "👩‍🏫 Caregiver View" button on the welcome screen.

---

## 🗂️ File Structure

```
feelings-friends.html    ← Entire application (single file, no dependencies)
README.md                ← This file
```

This is intentionally a **single-file application**. Everything — HTML, CSS, JavaScript, and SVG assets — is bundled together for maximum portability. No npm, no build step, no internet connection required after initial load.

---

## 📊 Caregiver Dashboard

The dashboard is accessible from the welcome screen via the **"👩‍🏫 Caregiver View"** button.

### What caregivers see

```
┌──────────────────────────────────────────────────────┐
│  Stats: 14/20 checked in today  |  😊 most common   │
├──────────────────────────────────────────────────────┤
│  Legend: 😊 Happy  😢 Sad  😠 Angry  😨 Scared ...  │
├────────┬──────┬──────┬──────┬──────┬──────┬──────┬──│
│  Name  │ Mon  │ Tue  │ Wed  │ Thu★ │ Fri  │ Sat  │Su│
├────────┼──────┼──────┼──────┼──────┼──────┼──────┼──│
│ Aiden  │  😊● │  😢● │  😌● │  😠● │      │      │  │
│ Bella  │  😌● │  😊● │  😊● │  😊● │      │      │  │
│  ...   │  ... │  ... │  ... │  ... │      │      │  │
└────────┴──────┴──────┴──────┴──────┴──────┴──────┴──┘
```

Each filled cell shows the emotion face + a color dot representing the color the child associated with their feeling.

### Pre-loaded roster (customizable in code)

The app ships with 20 example names:
`Aiden, Bella, Carlos, Daisy, Elijah, Fiona, Gabe, Hannah, Isaac, Jade, Kai, Luna, Mason, Nina, Oscar, Penny, Quinn, River, Sofia, Theo`

To customize, edit the `ROSTER` array in the JavaScript section.

---

## 🔧 Customization

### Changing the roster

```javascript
// Find this array in the <script> section
const ROSTER = [
  'Aiden','Bella','Carlos','Daisy','Elijah',
  // Replace with your children's names
  'Your','Names','Here',...
];
```

### Adding or removing emotions

Each emotion is defined in the HTML as a `.emotion-btn` with an inline SVG face. The color variables are set in `:root`. To add a new emotion, duplicate an existing button block and update the SVG path data and color variables.

### Changing stickers

```javascript
// Find this array in the <script> section
const STICKERS = ['⭐','🌈','❤️','🌸','🦋','🐶','🌟','🌙','🎈','🌺','🐱','🦄','🌊','☀️','🍀','🎵','🐸','🍭','🎨','🏆'];
// Add, remove, or reorder emoji as needed
```

### Changing the color palette

```javascript
const COLORS_LIST = [
  {n:'Sun Yellow', h:'#FFD93D'},
  {n:'Sky Blue',   h:'#74B3CE'},
  // Add your own {n:'Name', h:'#HEXCODE'} entries
];
```

---

## 💾 Data & Privacy

- **All data is stored locally** in the browser's `localStorage` under the key `ff-data-v2`
- **No data is transmitted** to any server
- **No accounts, logins, or tracking** of any kind
- Data persists across browser sessions until the browser cache is cleared
- The "Clear today" button in the caregiver dashboard removes only today's entries
- Clearing browser data / site data will erase all stored check-ins

> ⚠️ **Important:** Because data is stored in `localStorage`, it is tied to the specific browser and device. If you use the app on multiple devices, check-ins do not sync between them. For multi-device or multi-staff use, consider hosting the file on a shared device or local network.

---

## ♿ Accessibility

- All emotion buttons are `<button>` elements with appropriate touch target sizing (minimum 44×44px)
- Color is never the sole differentiator — each emotion has a distinct illustrated face and label
- Large, high-contrast text throughout (Nunito 800–900 weight)
- No time-limited interactions
- Touch events and mouse events both supported
- `user-scalable=no` is set intentionally to prevent accidental zoom during child use; remove this meta tag if accessibility zoom support is needed

---

## 🧩 Part of a Larger Suite

Feelings Friends is part of a multi-tool emotional wellness suite:

| Tool | Ages | Description |
|------|------|-------------|
| **Feelings Friends** *(this tool)* | 1–5 | Illustrated faces, color picker, sticker canvas, caregiver dashboard |
| **Feelings Explorer** | 5–10 | Flip cards with definitions, multi-select emotions, intensity sliders, finger drawing |
| **Check In** | 11–17 | Body map, triggers, journal prompts, intensity tracking, optional counselor sharing |
| **Mindscape** | Adults | Full Plutchik emotion wheel, mood journal, CBT tools 
```

---

## 🙏 Acknowledgments

- Emotion framework informed by developmental psychology research on early childhood emotional literacy
- Face designs inspired by the work of clinical child psychologists and art therapists
- Built with care for the children, caregivers, and clinicians who use it every day

---

*Built with ❤️ for the little ones who don't have words yet.*
