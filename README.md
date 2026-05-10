# 🌐 Zonemate

**Find your study window, across any timezone.**

Zonemate helps two people in different timezones find their perfect study window — just add your free hours, and it shows exactly when you're both available, even across midnight.

Built for Anish (Florida 🇺🇸) and Venkatesh (India 🇮🇳).

---

## ✨ Features

- **Live analog + digital clocks** for EDT and IST, updated every second
- **Weekly availability scheduler** — pick any day in the next 7 days and set your free window
- **Cross-midnight support** — enter slots like 8 PM → 1 AM and the app handles the date rollover automatically
- **Instant overlap detection** — common study windows are calculated in real time across timezones
- **Portrait / landscape toggle** — side-by-side clock view for wider screens
- **Zero dependencies** — pure HTML, CSS, and JavaScript. No frameworks, no build step.

---

## 🚀 Live Demo

[zonemate-av.netlify.app](https://zonemate-av.netlify.app)

---

## 🛠️ Getting Started

No install needed. Just open the file.

```bash
git clone https://github.com/your-username/zonemate-av.git
cd zonemate-av
open index.html
```

Or drag `index.html` into any browser.

---

## 📦 Deploying to Netlify

1. Push this repo to GitHub
2. Go to [netlify.com](https://netlify.com) → **Add new site** → **Import from Git**
3. Select your repo
4. Set publish directory to `/` (root)
5. Click **Deploy** — done ✅

No build command needed.

---

## 🕐 How the Timezone Math Works

Each availability slot is stored as local minutes (0–1439) anchored to a calendar date. When computing overlaps, both slots are converted to **absolute UTC minutes** using:

```
absUTC = dayIndex × 1440 + localMinutes − tzOffset
```

This correctly handles:
- EDT (UTC−4) and IST (UTC+5:30) — a 9h 30min gap
- Cross-midnight slots (e.g. 8 PM → 1 AM) split into two date-anchored segments
- Overlaps that land on different calendar dates for each person

---

## 📁 Project Structure

```
zonemate-av/
├── index.html      # Everything — HTML, CSS, JS in one file
├── README.md
└── LICENSE
```

---

## 🤝 Built For

| Person | Location | Timezone |
|--------|----------|----------|
| Anish | Florida, USA | EDT (UTC−4) |
| Venkatesh | India | IST (UTC+5:30) |

---

## 📄 License

MIT License — see [LICENSE](./LICENSE) for details.
