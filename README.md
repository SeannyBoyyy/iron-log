# Iron Log

A no-nonsense progressive overload tracker built as a PWA — installable on your phone, works fully offline, stores everything locally. No account, no cloud, no ads.

![Iron Log](icon-512.png)

---

## What it does

Iron Log is built around one question: **am I actually getting stronger?**

You set up your training split (Push / Pull / Legs / Rest or any pattern you want), assign exercises to each day, and log your weight and reps every session. The app tracks a two-session streak per exercise — once you hit the top of your rep range across all sets in two sessions in a row at the same weight, it tells you it's **Time to Ascend** and pre-fills the next suggested weight automatically.

No noise. No social features. Just your lifts and whether you're progressing.

---

## Features

- **Custom split builder** — any pattern (PPL/Rest, Upper-Lower, 5-day, etc.), any number of days
- **Per-exercise configuration** — sets, rep range (min–max), and your own weight increment (e.g. 2.5kg for compounds, 1kg for isolation)
- **Progressive overload detection** — fires after hitting your rep target on all sets, two sessions in a row
- **Time to Ascend badge** — clear visual cue when it's time to add weight, with suggested weight pre-filled
- **Streak dots** — two dots per exercise showing your current streak toward the ascend trigger
- **Session history** — sparkline chart + last 6 sessions per exercise in the Progress tab
- **Dynamic sets** — add or remove sets mid-workout without affecting your saved program
- **Exercise reordering** — ↑↓ arrows to reorder exercises within a day
- **Undo remove** — 4-second undo toast when removing an exercise from a day
- **Cycle sync** — jump to any day in your cycle if it gets out of sync with real life
- **Export / Import** — full JSON backup so your data is never locked in
- **PWA** — installs to your home screen, works completely offline
- **No account required** — all data stays on your device

---

## Deploying to GitHub Pages

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set source to **Deploy from branch → main → / (root)**
4. Your app will be live at `https://yourusername.github.io/iron-log/`

That's it. No build step, no CI, no configuration.

### Custom domain (optional)

Add a `CNAME` file to the repo root containing your domain (e.g. `ironlog.app`) and configure your DNS per [GitHub's documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

### Installing as a PWA

Once hosted, open the URL on your phone browser:
- **Android (Chrome):** tap the three-dot menu → "Add to Home Screen"
- **iOS (Safari):** tap the Share button → "Add to Home Screen"

After installing, the app runs offline — no internet needed at the gym.

---

## Files

```
iron-log/
├── index.html          # Entire app — HTML, CSS, and JS in one file
├── manifest.json       # PWA manifest
├── sw.js               # Service worker for offline support
├── icon-192.png        # PWA icon (any)
├── icon-512.png        # PWA icon (any)
└── icon-512-maskable.png  # PWA icon (maskable, for Android adaptive icons)
```

All five files must stay in the same directory for the PWA to install correctly.

---

## Local development

No build tools required. Just open `index.html` in a browser — or serve it locally for full PWA/service worker support:

```bash
# Python 3
python3 -m http.server 8080

# Node (npx)
npx serve .
```

Then open `http://localhost:8080`.

> Service workers only register on `localhost` or HTTPS. If you open `index.html` directly via `file://`, the offline cache won't activate (but the app itself works fine).

---

## Data and privacy

Everything is stored in your browser's `localStorage`. Nothing is sent anywhere. Clearing site data in your browser will wipe your history — use **Settings → Export backup** to keep a copy before doing so.

The export produces a plain `.json` file you can back up anywhere or use to move your data to another device via **Settings → Import backup**.

---

## Built with

- Vanilla HTML / CSS / JavaScript — zero dependencies, zero build step
- Web App Manifest + Service Worker for PWA installability and offline support
- `localStorage` for persistence
- Oswald + Inter + IBM Plex Mono (Google Fonts)

---

## License

MIT — see [LICENSE](LICENSE).

Feel free to fork, modify, and host your own version.
