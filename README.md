# SPG-Health
# SPG Labs — Real Installable App (PWA) — Setup Guide

Ab app **seedha install** hota hai (shortcut nahi). Data wahi Google Sheet se aata hai.

## Folder structure
```
spg-labs/                    ← GitHub Pages par upload (HTTPS, free, permanent)
├── index.html               ← poora SPG Labs app (phone interface ke saath)
├── manifest.json
├── sw.js
├── offline.html
└── icons/
    ├── icon-192.png
    ├── icon-512.png
    ├── maskable-512.png
    ├── apple-touch-icon.png
    └── icon.svg             (sirf source)

Google Apps Script project
├── Code.gs                  ← same, koi change nahi
├── Api.gs                   ← NAYI file (apps-script/Api.gs)
├── report.html / backup.gs  ← same
└── index (HTML file)        ← ab zarurat nahi — rakho ya delete, dono chalega
```

## Step 1 — Apps Script
1. Editor me **+ → Script** → naam `Api` → `apps-script/Api.gs` ka poora code paste → Save.
2. **Deploy → Manage deployments → ✏️ Edit → Version: New version → Deploy**
   (Execute as: **Me**, Who has access: **Anyone**).
3. Web app URL (`.../exec`) copy karo.

## Step 2 — GitHub Pages
1. github.com → free account → **New repository** `spg-labs` (Public).
2. **uploading an existing file** → folder ke andar ki saari files + `icons` folder drag karo → Commit.
3. **Settings → Pages** → Branch `main`, `/ (root)` → Save. 1–2 min baad link: `https://USERNAME.github.io/spg-labs/`

## Step 3 — Phone
1. Chrome me link kholo → pehli baar `/exec` URL paste → Save & Open App → login.
2. Green **⬇️ Install App** (login screen par bhi aur upar header me) → Install.
3. Ab home screen icon se app bina URL bar ke khulega, neeche tab bar dikhega.
4. Icon long-press → New Record / Records / Bookings / Lab Report.
5. Purana shortcut (jo pehle bana tha) delete kar do.

URL baad me badalna ho: `.../index.html?setup=1` kholo.
Seedha code me daalna ho: `index.html` me `var GAS_URL = "";` me paste karo.

## Chrome check (desktop)
F12 → Application → Manifest (no errors, 4 shortcuts), Service workers (activated), Cache storage.
Lighthouse → PWA.

## iPhone
Safari → link → Install App → Share ⎋ → Add to Home Screen. (iOS me long-press shortcuts nahi hote.)

## Update karna ho
Files badlo → `sw.js` me `VERSION` badhao → GitHub par dobara upload.
