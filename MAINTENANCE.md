# fokofpolisiekar.com — Maintenance Guide

## 1. Overview

**Die Informele Museum** is an unofficial fan archive celebrating 20+ years of Fokofpolisiekar and South African rock history.

- **Live at:** [fokofpolisiekar.com](https://fokofpolisiekar.com)
- **Hosted on:** GitHub Pages (auto-deploys on `git push` to `main`)
- **Repo:** [github.com/SoberMountainMan/fokofpolisiekar](https://github.com/SoberMountainMan/fokofpolisiekar)
- **Maintained by:** JP (content) + WildLogic (technical)
- **Cost:** R0/month hosting. 100% pasella.

The entire site lives in a single file: `index.html`. All CSS is inside a `<style>` block at the top. No JavaScript frameworks. No build tools. Just HTML.

---

## 2. How to Deploy

Every change follows the same flow:

1. **Edit** `index.html` (in GitHub or locally)
2. **Save** the file
3. **Commit** with a clear message (e.g. "Add new show date to timeline")
4. **Push** to `main`
5. **Wait** 1–2 minutes — GitHub Pages auto-deploys

### Editing on GitHub (no software needed)

1. Go to the repo: `github.com/SoberMountainMan/fokofpolisiekar`
2. Click on `index.html`
3. Click the pencil icon (Edit this file)
4. Make your changes
5. Scroll down. Write a commit message describing what you changed
6. Click **Commit changes**
7. Wait 1–2 minutes, then refresh fokofpolisiekar.com

### If something breaks

- **Quick undo:** `git revert HEAD` — undoes the last commit
- **Full rollback:** `git checkout v1-holding-page -- index.html` — restores the original holding page
- Both options deploy automatically on push

---

## 3. Section-by-Section Edit Guide

Each editable section in `index.html` has an HTML comment marker above it. Search for these to find where each section starts:

| Section | Edit Marker | What It Does |
|---|---|---|
| Hero / Backstory | *(no marker yet — between `<header>` and `<main>`)* | Origin story, tagline, "Gooi Man" quote |
| Band Ecosystem Link Hub | `<!-- EDIT: Band Ecosystem Link Hub -->` | Grid of link cards to band properties |
| Discography Vault | `<!-- EDIT: Discography Vault -->` | Album cards with Spotify embeds |
| Interactive Timeline | `<!-- EDIT: Interactive Timeline -->` | Vertical milestone timeline |
| Pasella Manifesto | *(inside `<main>`, near the bottom)* | 0% revenue notice |
| Disclaimer | *(inside `.band-section`)* | Legal disclaimer text |

### 3.1 Hero / Backstory

**Where:** Top of the page, between `<header>` and `<main>`. The `<div class="backstory">` block.

**What you might edit:**
- The origin story text (the Afrikaans paragraph and English translation)
- The tagline: *"Some revolutions are worth keeping alive..."*
- The quote: *"Dink jy 'n man op die domein is 'n goeie idee?"*

**What NOT to touch:**
- The `<h1>` gradient animation CSS
- The `class="kicker"` or `class="quote"` attributes

**How to verify:** Open the site on your phone. The hero should look clean with the animated title.

### 3.2 Band Ecosystem Link Hub

**Where:** Find `<!-- EDIT: Band Ecosystem Link Hub -->`. Below it is a `<div class="link-hub">` containing link cards.

**What you might edit:**
- Update a URL (if a band changes their website)
- Change a card name or description
- Add a new band/project card

**What NOT to touch:**
- The CSS classes (`link-card`, `link-card-name`, etc.)
- The `target="_blank" rel="noopener"` attributes (these are security essentials)

**How to verify:** Click every link in the hub. Each should open the correct site in a new tab.

### 3.3 Discography Vault

**Where:** Find `<!-- EDIT: Discography Vault -->`. Below it is `<section class="discography">` with a `<div class="disco-grid">` containing album cards.

**What you might edit:**
- Add a new album release
- Update a Spotify embed URL
- Fix album artwork

**What NOT to touch:**
- The `disco-grid` or `disco-card` class names
- The `<iframe>` attributes other than `src`

**How to verify:** Scroll through all album cards. Spotify players should load and play. Check on mobile — cards stack to single column below 600px.

### 3.4 Interactive Timeline

**Where:** Find `<!-- EDIT: Interactive Timeline -->`. Below it is `<section class="timeline">` with a `<div class="timeline-track">` containing milestones.

**What you might edit:**
- Add a new milestone (show date, album release, band news)
- Fix a factual error
- Update the correction email

**What NOT to touch:**
- The `::before` pseudo-element CSS (the red dots on the timeline)
- The `.milestone-year` or `.milestone-content` class names
- The border-left styling on `.timeline-track`

**How to verify:** Scroll the full timeline. Each milestone should have a red dot, a year, and content text. Check mobile — the vertical line and dots should align properly.

### 3.5 Pasella Manifesto

**Where:** Inside `<main>`, near the bottom. The `<div class="pasella-note">` block.

**What it says:** "Alle skakels is pasella. 0% kommissie. 100% van strome en verkeer gaan direk na die band en amptelike kanale."

**This rarely needs editing.** Only change if the band's relationship changes.

### 3.6 Disclaimer

**Where:** Inside the `.band-section` div. The `<p class="disclaimer-text">` block.

**What it says:** Trademarks belong to respective owners. No copyrighted content hosted. All links point to official channels.

**This rarely needs editing.** Only change if legal requirements change.

---

## 4. Common Tasks (Recipes)

### Recipe: Add a new show date to the timeline

Find the `<!-- EDIT: Interactive Timeline -->` marker. Inside the `<div class="timeline-track">`, add a new milestone block at the correct chronological position:

```html
<div class="milestone">
  <div class="milestone-year">2026</div>
  <div class="milestone-content">New album <em>Post-Afrikaner</em> announced. Release date TBA.</div>
</div>
```

**Tips:**
- Keep the year in `milestone-year` — it displays in red
- Use `<em>` for album/release names (italic)
- Keep it factual and brief. One or two sentences max.
- Place milestones in chronological order

### Recipe: Add a new album to the discography

Find the `<!-- EDIT: Discography Vault -->` marker. Inside the `<div class="disco-grid">`, add a new card:

```html
<div class="disco-card">
  <div class="disco-art">
    <img src="SPOTIFY_ARTWORK_URL" alt="ALBUM NAME cover" loading="lazy" decoding="async" fetchpriority="low" onerror="this.style.display='none'">
  </div>
  <div class="disco-info">
    <h3>ALBUM NAME</h3>
    <div class="disco-year">YEAR &middot; Album</div>
    <div class="disco-embed">
      <iframe src="https://open.spotify.com/embed/album/SPOTIFY_ALBUM_ID" width="100%" height="80" frameborder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy" style="border-radius:12px"></iframe>
    </div>
    <a href="APPLE_MUSIC_URL" target="_blank" rel="noopener" class="disco-link">Apple Music &rarr;</a>
  </div>
</div>
```

**How to find the values:**
1. Open the album on Spotify → click Share → copy link
2. The embed URL is: `https://open.spotify.com/embed/album/XXXXX` (the XXXXX is the album ID from the Spotify link)
3. For artwork: right-click the album art on Spotify → Copy image address
4. For Apple Music: find the album on Apple Music → copy the URL

### Recipe: Update a broken link

1. Find the broken link in the browser (it won't load or goes to the wrong place)
2. In `index.html`, search for the old URL
3. Replace it with the new URL
4. Make sure `target="_blank" rel="noopener"` stays on the link

**Example — fixing a link card URL:**
```html
<!-- Before -->
<a href="https://old-url.com" target="_blank" rel="noopener" class="link-card">

<!-- After -->
<a href="https://new-url.com" target="_blank" rel="noopener" class="link-card">
```

### Recipe: Add a new band to the link hub

Find `<!-- EDIT: Band Ecosystem Link Hub -->`. Inside the `<div class="link-hub">`, add a new card:

```html
<a href="https://their-website.com" target="_blank" rel="noopener" class="link-card">
  <div class="link-card-name">Band Name</div>
  <div class="link-card-desc">Short description</div>
  <span class="link-card-arrow">&rarr;</span>
</a>
```

**Tips:**
- Always include `target="_blank" rel="noopener"` — opens in new tab, securely
- Keep descriptions short (2–4 words)
- Only link to official band channels

---

## 5. Style Guide

### Colors

Defined as CSS custom properties in `:root`:

| Variable | Value | Used For |
|---|---|---|
| `--bg-color` | `#0a0a0a` | Page background (near-black) |
| `--card-bg` | `#141414` | Card backgrounds |
| `--accent-red` | `#ff2a2a` | Highlights, buttons, timeline dots, links |
| `--text-main` | `#e0e0e0` | Body text |
| `--text-muted` | `#888888` | Secondary text, captions |
| `--border-color` | `#262626` | Card borders, dividers |

### Fonts

| Font | Used For | Loaded From |
|---|---|---|
| **Bebas Neue** | All headings (h1, h2, h3, buttons) | Google Fonts |
| **Courier Prime** | Body text, paragraphs | Google Fonts |

### Spacing

- Cards: `2rem` padding, `2rem` margin-bottom between cards
- Section gaps: `1.5rem–2rem` margin-top
- Container max-width: `900px`

### Responsive Breakpoints

| Width | What Changes |
|---|---|
| Above 600px | Discography grid: 2 columns. Link hub: 2 columns. |
| 480px and below | Link hub: 1 column. |
| 600px and below | Discography grid: 1 column. |

---

## 6. Troubleshooting

### Site not updating after push?

- Wait 2 minutes. GitHub Pages needs time to deploy.
- Hard-refresh your browser: **Ctrl+Shift+R** (Windows) or **Cmd+Shift+R** (Mac)
- Check the repo's **Actions** tab — is the deploy still running?
- Try opening the site in an incognito window

### Spotify embed not showing?

- Check the embed URL format: `https://open.spotify.com/embed/album/ALBUM_ID`
- Make sure the album is still on Spotify (search for it first)
- Check that the `<iframe>` tag is complete and properly closed
- Some ad blockers hide iframes — try disabling yours

### Image not loading?

- Check the image URL — it should start with `https://i.scdn.co/image/`
- The `onerror="this.style.display='none'"` attribute hides broken images gracefully
- If artwork is missing, the card shows a dark empty square — this is expected behaviour until the URL is fixed

### Something looks broken on mobile?

- Open Chrome DevTools (F12) → toggle device toolbar → check at 320px width
- The link hub and discography grid switch to single-column on small screens
- If text overflows, check that no hardcoded widths are set
- The h1 title uses `clamp()` for responsive sizing — it should scale automatically

### A link goes to the wrong place?

- Search `index.html` for the link text to find it quickly
- Verify the `href` value
- Make sure `target="_blank"` is present so it opens in a new tab

---

## 7. Contact

- **WildLogic:** [wildlogic.co.za](https://wildlogic.co.za)
- **Email for corrections:** [info@wildlogic.co.za](mailto:info@wildlogic.co.za)
- **GitHub repo:** [github.com/SoberMountainMan/fokofpolisiekar](https://github.com/SoberMountainMan/fokofpolisiekar)
- **Report a bug:** Open an issue on GitHub or email WildLogic

### Before asking for help

1. Try the troubleshooting steps above
2. Note exactly what you see vs. what you expected
3. Include the URL of the page and what device/browser you're using
4. If you made a change that broke something, note the commit message

---

*Laaste opdatering: 2026-07-31*
