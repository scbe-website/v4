# SoCal Bradley Electric — Website

Single-page website. Plain HTML/CSS/JS — no build step, no frameworks.

---

## 📁 File Structure

```
socal-bradley-site/
├── index.html
├── README.md
└── images/
    ├── logo.png               ✅ Already included
    ├── hero-bg.jpg            ← ADD: Full-screen hero background photo
    │
    │  ── Service Panel Detail Photos (show when breaker is clicked) ──
    ├── res-01.jpg             ← Ceiling Fans
    ├── res-02.jpg             ← Dimmers & Smart Switches
    ├── res-05.jpg             ← Smoke & CO Detectors
    ├── res-06.jpg             ← Utilities Coordination
    ├── res-09.jpg             ← LED Lighting
    ├── res-10.jpg             ← EV Chargers
    ├── res-13.jpg             ← RV / Trailer Power
    ├── res-14.jpg             ← General Electrical
    ├── res-15.jpg             ← Panel Upgrades
    ├── com-01.jpg             ← Tenant Improvements
    ├── com-02.jpg             ← Biotech Labs
    ├── com-05.jpg             ← Medical Buildings
    ├── com-06.jpg             ← Emergency / Generator Systems
    ├── com-09.jpg             ← 3-Phase Power
    ├── com-10.jpg             ← Instrument Circuits
    ├── com-13.jpg             ← Commercial Service Calls
    ├── com-14.jpg             ← Commercial LED Lighting
    ├── com-15.jpg             ← New Construction
    │
    │  ── Service Icon Grid (circle photos above the panels) ──
    ├── panel-upgrade.jpg      ← Panel Upgrades circle
    ├── ev-charger.jpg         ← EV Charger circle
    ├── biotech-lab.jpg        ← Biotech & Lab circle
    ├── led-lighting.jpg       ← Lighting circle
    ├── wiring-repair.jpg      ← Electrical Repairs circle
    ├── rv-hookup.jpg          ← RV & Trailer circle
    ├── ceiling-fan.jpg        ← Ceiling Fan circle
    └── tenant-improvement.jpg ← Tenant Improvements circle
```

---

## 📸 How to Add Photos

### 1. Hero Background

Save any dark dramatic photo (lab, commercial job site, electrical panel) as:
**`images/hero-bg.jpg`**

The gradient overlay darkens it automatically — any photo works.
Free photos: [unsplash.com](https://unsplash.com) → search "electrical panel" or "laboratory"
Recommended size: 1920×1080px or larger.

---

### 2. Service Panel Photos (the detail readout when you click a breaker)

Each breaker loads a photo from `images/` based on its number prefix.

- Breaker 01 on Residential → loads `images/res-01.jpg`
- Breaker 02 on Commercial  → loads `images/com-02.jpg`
- etc.

**Steps:**
1. Get a photo for that service (job site photos from your phone are perfect)
2. Name it to match the filename list above (e.g. `res-10.jpg` for EV Chargers)
3. Drop it into the `images/` folder
4. Click that breaker on the website — photo appears automatically

If a file doesn't exist yet, a placeholder shows instead. Nothing breaks.
Recommended size: 440×400px (landscape). JPG or PNG both fine.

---

### 3. Service Icon Grid Photos (circles in "What We Do")

These are the round circle photos like in the reference image you shared.

1. Save a photo and name it from the list above (e.g. `panel-upgrade.jpg`)
2. Drop it in `images/`
3. In `index.html`, find the matching `<img src="">` tag — it has a comment next to it showing the filename
4. Change `src=""` to `src="images/panel-upgrade.jpg"`

Square photos work best (400×400px) — they're displayed as circles so the center shows.

---

## 🗺️ Add a Google Map

1. Go to [maps.google.com](https://maps.google.com) → search San Diego, CA
2. Click Share → Embed a map → copy the `<iframe>` code
3. In `index.html`, find `<div class="area-map">` and replace the whole block with your iframe
4. Add to the iframe tag: `style="width:100%;height:290px;border-radius:8px;border:0;"`

---

## 📬 Contact Form

The form has `data-netlify="true"` — works automatically on Netlify (free hosting).

For GitHub Pages, use [Formspree](https://formspree.io) (free):
1. Sign up at formspree.io
2. Create a new form, copy your form ID
3. In `index.html` find `<form` and add: `action="https://formspree.io/f/YOUR_ID"`

---

## 🚀 GitHub Pages Deployment

1. Create a new GitHub repo
2. Upload everything from this folder (keep `images/` folder intact)
3. Settings → Pages → Deploy from branch → main → / (root) → Save
4. Site goes live at `https://yourusername.github.io/repo-name`

**Connect your domain:**
- Settings → Pages → Custom domain → enter `socalbradleyelectric.com`
- In your domain registrar DNS, add 4 A records:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
- Add CNAME: `www` → `yourusername.github.io`
- Check "Enforce HTTPS" once DNS propagates (up to 48 hours)

---

## ✏️ Quick Edits

| What | Where in index.html |
|---|---|
| Phone number | Search `619-333-6470` — replace all instances |
| License number | Search `1131979` — replace all |
| Service descriptions | `RES` / `COM` arrays in the `<script>` block at bottom |
| FAQ answers | `<details class="fi">` blocks |
| Business hours | Contact section, find `Mon–Fri 7am–6pm` |
| Instagram | Find `@socalbradleyelectric` |
| Hero headline | `<h1>` inside `<section class="hero">` |
