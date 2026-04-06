# SoCal Bradley Electric — Website

Single-page website for SoCal Bradley Electric. Built with plain HTML/CSS/JS. No build step required.

## File Structure

```
socal-bradley-site/
├── index.html          ← Main website (all sections)
├── images/
│   └── logo.png        ← ✅ Logo file (already included)
└── README.md           ← This file
```

## 📸 Adding Service Photos

Each breaker in the service panels has a photo placeholder. To add real photos:

1. Drop image files into the `images/` folder (e.g. `images/ev-charger.jpg`)
2. Open `index.html` and find the `RES` or `COM` breaker data arrays at the bottom in the `<script>` tag
3. Add an `img` property to the matching breaker object:
   ```js
   { num:'10', name:'EV Chargers', ..., img:'images/ev-charger.jpg' },
   ```
4. Save — the photo will now appear in the detail panel when that breaker is clicked

## 🚀 GitHub Pages Deployment

1. Create a new repository on GitHub (e.g. `socalbradleyelectric`)
2. Push this folder's contents to the `main` branch
3. Go to **Settings → Pages**
4. Set Source to **"Deploy from branch"** → `main` → `/ (root)`
5. Click **Save**
6. Your site will be live at `https://yourusername.github.io/socalbradleyelectric`

### Connect your custom domain

1. In **Settings → Pages → Custom domain**, enter `socalbradleyelectric.com`
2. Click **Save**
3. In your domain registrar's DNS settings, add:
   - Type: `A` → `185.199.108.153`
   - Type: `A` → `185.199.109.153`
   - Type: `A` → `185.199.110.153`
   - Type: `A` → `185.199.111.153`
   - Type: `CNAME` → `www` → `yourusername.github.io`
4. Check **Enforce HTTPS** once DNS propagates (can take up to 48 hours)

## ✏️ Common Edits

| What to change | Where in index.html |
|---|---|
| Phone number | Search `619-333-6470` — replace all |
| Service descriptions | `RES` / `COM` arrays in `<script>` |
| FAQ answers | `<details class="faq-item">` blocks |
| Business hours | Contact section `.c-info-val` for hours row |
| Instagram handle | `@socalbradleyelectric` link in contact |
| License number | Search `1131979` — replace all |

## 📬 Contact Form

The form uses `data-netlify="true"` for Netlify hosting. If using GitHub Pages:
- Use [Formspree](https://formspree.io) — add `action="https://formspree.io/f/YOUR_ID"` to the `<form>` tag
- Or [Web3Forms](https://web3forms.com) — similar setup, free tier available

## License
All rights reserved — SoCal Bradley Electric 2025
