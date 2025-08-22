# Blinds Estimator (3 Tabs)

A self-contained HTML calculator for **Combi**, **Roller**, and **PVC Vertical & Other** blinds.
- Min area: **15 ft²** (Combi/PVC also enforce min height **36"**).
- Roller formula: **unit price = (base × 2) + 15 + 30 + chain + bottom-tube + (Magic? +20)**.
- “Hi Client name, Good day po 😊, Eto po ang price para po sa N panels of blinds po ₱TOTAL.” message + **Copy** button.

## Files
- `index.html` — the full calculator (no build step required).

## Local Use
Just open `index.html` in any modern browser (Chrome, Edge, Safari, Firefox). Works offline.

## Deploy to GitHub Pages
1. Create a new repo on GitHub (or use an existing one).
2. Add these files and push:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Add 3-tab blinds estimator"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages**  
   - **Source:** Deploy from branch  
   - **Branch:** `main` / **root** (or put `index.html` inside a `docs/` folder and select `/docs`)

Your site will publish at the URL GitHub shows (e.g., `https://YOUR_USERNAME.github.io/YOUR_REPO/`).

## IMPORTANT — Private Pricing
This page hides pricing from customers, but **base prices are embedded** in the source code (needed for offline math).  
If your repo is **public**, anyone can view-source and see them. Options:
- Make the repo **private**, or
- Move the price list to a **private API** (then load via fetch with a token), or
- Simple obfuscation (not secure): store prices base64-encoded and decode at runtime.

If you want, I can set up a small JSON loader and show you how to keep codes public and prices private.

## Customize
Open `index.html` and look for these sections:
- **Price tables:** `COMBI_CODES`, `ROLLER_CODES`, `OTHER_CODES` → update codes or base prices.
- **Roller formula:** inside `r_lineCompute`. Currently `(base*2 + 15 + 30) + chain + btube + magic`.
- **Colors:** in CSS `:root` (`--c-combi`, `--c-roller`, `--c-pvc`).
- **Greeting/message:** search for `.announce` and `baseMsg` strings.
- **Logo/header:** change `<h1>Blinds Estimators</h1>` or add your logo image.

## Notes
- The Roller tab has a **reference image** uploader; the selected image is stored in the browser’s **localStorage**.
- CSV export buttons create a downloadable file of the current tab’s items.

— Packaged on 2025-08-22
