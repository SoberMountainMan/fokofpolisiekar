# fokofpolisiekar.com

Landing page for **fokofpolisiekar.com** — a WIP / coming-soon stub hosted on GitHub Pages.

Part of the [WildLogic](https://wildlogic.co.za) project portfolio.

---

## What this is

A single-file static landing page (`index.html`) with a punk/alternative coming-soon aesthetic. No build step, no dependencies, no JavaScript — just HTML and inline CSS.

## Deploying to GitHub Pages

This repo is designed to be served directly from the repository root via GitHub Pages:

1. Push this repo to GitHub (suggest repo name: `fokofpolisiekar`).
2. Go to **Settings → Pages**.
3. Under **Source**, select **Deploy from a branch**.
4. Set branch to **`main`** (or `master`) and folder to **`/ (root)`**.
5. Save. GitHub Pages will serve `index.html` from the repo root.

### Alternative: `docs/` folder

If you later add project files you don't want served, move `index.html` into a `docs/` folder and set the Pages source to **`/docs`** instead.

### Custom domain

Once GitHub Pages is live:

1. In **Settings → Pages → Custom domain**, enter `fokofpolisiekar.com`.
2. At your domain registrar, add DNS records pointing to GitHub Pages:
   - **A records** for `@` pointing to GitHub's IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - **CNAME** for `www` pointing to `<your-username>.github.io`
3. Enable **Enforce HTTPS** in GitHub Pages settings.

---

## Project ledger

This project is tracked in the WildLogic HQ ledger at `C:\WildLogic\WILDLOGIC-HQ.md`. The project-level ledger lives at `c:\WildLogic\fokofpolisiekar\ORCHESTRATOR.md`.
