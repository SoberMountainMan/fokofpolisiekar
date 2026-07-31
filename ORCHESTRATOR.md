# ORCHESTRATOR.md — fokofpolisiekar.com

**Maintained by:** HQ orchestrator chat (no dedicated project-orchestrator chat yet)
**Last updated:** 2026-07-31
**Purpose:** Master ledger for the fokofpolisiekar.com project — "Die Informele Museum", an unofficial fan archive for the SA band Fokofpolisiekar. Static, multi-section site hosted on GitHub Pages. Funded by JP (superfan). The band explicitly doesn't want the .com domain (they're 100% .co.za).

---

## §1 How This Works

- **HQ-owned directly.** No project-orchestrator chat or track chats opened yet. HQ reads and writes this ledger on its own syncs.
- **Ledger is a read-only index** at this scale — if a source doc disagrees with this file, the source doc wins and this file gets fixed.
- **When the project grows** (multiple pages, content tracks, automation), open a dedicated project-orchestrator chat on `C:\WildLogic\fokofpolisiekar\` and hand the ledger to it. That chat then owns this file and triages for its own tracks.
- **Routing DOWN (HQ → project):** HQ appends an `HQ NOTE — YYYY-MM-DD` section at the end of this file. The owning chat triages it on next sync.
- **Routing UP (project → HQ):** HQ reads this ledger's status board + maintenance log on its own syncs. Prefix `HQ:` in the maintenance log for urgent flags.
- **Writing standard:** All output follows `C:\WildLogic\WILDLOGIC-WRITING-STANDARDS.md`. AI agents: apply the 10 ADHD-friendly output rules + pre-send check.

---

## §2 Track Status Board

| Track | Scope | State | Owner | Notes |
|---|---|---|---|---|
| WIP holding page deployment | Replace parody with "Aan die Bou" holding page at fokofpolisiekar.com | **DONE** | HQ | Deployed 2026-07-31. Parody retired. Includes "Die Band" section with unofficial disclaimer, pasella manifesto, Spotify + .co.za CTAs. |
| Die Informele Museum (full build) | Multi-section static fan archive — hero, pasella manifesto, band ecosystem hub, discography vault, interactive timeline | **ALL SECTIONS LIVE** | HQ | All sections deployed: backstory, link hub, discography vault, timeline. Responsive pass done. WIP badge removed. Performance optimized. |

---

## §3 Activation Pipeline

| Step | Action | State | Notes |
|---|---|---|---|
| 1 | Deploy WIP holding page (retire parody) | **DONE** | Holding page deployed 2026-07-31. Parody retired. Includes "Die Band" section with unofficial disclaimer, pasella manifesto, Spotify + .co.za CTAs. |
| 2 | Source timeline content from online sources | ⬚ | Annie Klopper's *Biografie van 'n bende* not incoming. Use public band history, LitNet archives, album release years, famous band lore. |
| 3 | Build hero section + pasella manifesto | **DONE** | Backstory ("Die Storie"), EP artwork frame, museum archive section, pasella note. Steps 1-3 of museum build complete (backstory, link hub, discography vault). |
| 4 | Build band ecosystem link hub | **DONE** | 6 link cards: FPK official, Francois van Coke, Annie Klopper, Fokof Lager, Van Coke Kartel, Die Heuwels Fantasties. |
| 5 | Build discography vault with Spotify embeds | **DONE** | 7 albums with corrected names: As Jy Met Vuur Speel Sal Jy Brand (2003), Lugsteuring (2004), Monoloog In Stereo (2005), Swanesang (2006), Antibiotika (2008), Selfmedikasie (2017), Dans Deur Die Donker (2023). All Spotify embeds lazy-loaded. Apple Music links. Container widened to 900px. Commit: `319e533`. |
| 6 | Build interactive timeline (2003–present) | **DONE** | 12 milestones (2003–2026). Vertical timeline with red dot markers. Correction mechanism (mailto link). Sources: Wikipedia, Spotify, Discogs, IOL, Bizcommunity. |
| 7 | Responsive pass + accessibility check | **DONE** | Mobile breakpoints at 480px and 600px. Accent red improved (#ff3333, 4.75:1 contrast). Timeline/card padding tightened on mobile. All images have alt text. All links descriptive. |
| 8 | Verify HTTPS + Cloudflare caching | ⬚ | Confirm cert coverage, edge caching, all URL variants |

---

## §4 Cross-Track Contracts — DO NOT BREAK

> No project-level contracts yet. Flag shared keys/gateways/schemas here BEFORE implementation as tracks emerge.

**Shared assets to be aware of (from HQ §4):**
- **WildLogic brand voice ("Wired Different")** — all projects use this per HQ §4 rulings. The fokofpolisiekar.com page carries a "A WildLogic project" footer line; brand voice applies to any future copy on this site.

---

## §5 Open Items

| Item | Status | Notes |
|---|---|---|
| Deploy WIP holding page (retire parody) | **DONE** | Deployed 2026-07-31. Commit: "retire parody: deploy Die Informele Museum WIP holding page". Includes band bio + unofficial disclaimer. |
| Set up GitHub repo + enable Pages | **DONE** | Repo: https://github.com/SoberMountainMan/fokofpolisiekar — Pages LIVE at https://sobermountainman.github.io/fokofpolisiekar/ |
| Point domain DNS | **DONE** | DNS propagated (cloudoon nameservers via Truehost). Custom domain `fokofpolisiekar.com` set in GitHub Pages. Let's Encrypt cert approved (covers apex + www, expires 2026-10-28). HTTPS enforced. All four URL variants verified working (http/https × apex/www) |
| Source timeline milestones from online sources | ⬚ TODO | Public band history, LitNet archives, album release years (2003–present), famous band lore (Stellenbosch origins, Witbank wall incident, hiatuses, Van Coke Kartel/Die Heuwels Fantasties spin-offs, reunion shows, Selfmedikasie 2017, Droom Hoog 2023). |
| Decide on fan nostalgia wall | ⬚ TODO | Phase 2+ feature. Needs backend decision (Formspree or similar). Not blocking Phase 1. |

---

## §6 Backlog / Ideas

- WildLogic brand site (`wildlogic.co.za`) is a separate asset at HQ level — no cross-pollination planned yet.

### Die Informele Museum — Build Plan

- **Vision:** Unofficial fan archive / digital museum celebrating 20+ years of Fokofpolisiekar and SA rock history.
- **Origin story:** Band said "Gooi man" when JP offered the domain back to them. Confirmed they're 100% .co.za ("homegrown"). JP (superfan) funding the project.
- **Tech stack:** Static HTML + Tailwind CSS on GitHub Pages (R0/month hosting). No WordPress, no database, no backend for Phase 1.
- **Sections:**
  - Hero + "Gooi Man" backstory — *As Jy Met Vuur Speel* artwork framed as museum artifact, tagline, CTAs to official .co.za and Spotify
  - Pasella manifesto — explicit 0% revenue cut disclaimer, all links go direct to band/official channels
  - Band ecosystem link hub — FPK official (.co.za), Francois van Coke, Annie Klopper, Fokof Lager, side projects (Van Coke Kartel, Die Heuwels Fantasties)
  - Interactive timeline (2003–present) — vertical milestone scroll: Stellenbosch origins, album eras, Witbank wall incident, hiatuses, reunion shows, Selfmedikasie (2017), Droom Hoog (2023)
  - Discography vault — 7 album cards with embedded Spotify/Apple Music iframe players (zero copyright risk, drives streaming revenue to band)
  - Fan nostalgia wall — Phase 2+ (needs backend decision: Formspree or similar)
- **Legal safeguards:** No direct asset hosting (embeds only), zero e-commerce, all merch/ticket CTAs deep-link to fokofpolisiekar.co.za, explicit "unofficial fan archive" disclaimer, pasella manifesto (0% revenue cut).
- **JP deal structure:** R5k once-off setup + R1k/month maintenance (if we proceed with this deal).

---

## §7 Ledger Maintenance Log

| Date | Change |
|---|---|
| 2026-07-29 | Ledger created. Project seeded by HQ: folder `C:\WildLogic\fokofpolisiekar\`, single-track scope (WIP landing page for fokofpolisiekar.com). HQ-owned directly — no project-orchestrator chat yet. Activation pipeline seeded (build page → GitHub repo → GitHub Pages → DNS). Awaiting: GitHub repo setup, Pages config, domain DNS. |
| 2026-07-30 | Content rewrite: parody positioning — tagline "Ons hou die domein vas." / "Bring shirts. Baie shirts." GitHub repo created (https://github.com/SoberMountainMan/fokofpolisiekar), code pushed, Pages enabled, CNAME committed. Site LIVE at https://sobermountainman.github.io/fokofpolisiekar/ — custom domain fokofpolisiekar.com pending DNS at Truehost.co.za. Built with Qwen Code. |
| 2026-07-30 | DNS propagated (cloudoon nameservers via Truehost, registrar NameSilo). Custom domain `fokofpolisiekar.com` set in GitHub Pages. Let's Encrypt cert approved — covers both `fokofpolisiekar.com` and `www.fokofpolisiekar.com`, expires 2026-10-28. HTTPS enforced. All four URL variants verified working: http://fokofpolisiekar.com → 301 → https://fokofpolisiekar.com → 200 OK; https://fokofpolisiekar.com → 200 OK; http://www.fokofpolisiekar.com → 301 → redirect; https://www.fokofpolisiekar.com → 301 → redirect to apex. |
| 2026-07-31 | Writing standard pointer added per HQ rollout. |
| 2026-07-31 | **PIVOT DECIDED:** Site pivoting from parody to "Die Informele Museum" — unofficial fan archive for Fokofpolisiekar. Full museum build plan documented in §6. Timeline content to be sourced from online sources (book not incoming). JP funding the project. Parody still live — WIP holding page deployment is next up. |
| 2026-07-31 | **HOLDING PAGE DEPLOYED.** Parody retired. "Die Informele Museum — Aan Die Bou" WIP page now live at fokofpolisiekar.com. Includes: band bio ("Die Band" section), unofficial/unaffiliated disclaimer, pasella manifesto, Spotify + .co.za CTAs, EP artwork fallback. Commit: `18a7dce`. |
| 2026-07-31 | **MUSEUM BUILD STEPS 1-3 DEPLOYED.** Step 1: Backstory ("Die Storie") added. Step 2: Band ecosystem link hub (6 cards). Step 3: Discography vault — 7 album cards with Spotify embeds (lazy-loaded) + Apple Music links. Album name corrections applied (Monoloog In Stereo, Swanesang, Dans Deur Die Donker). Container widened to 900px for 2-col grid. Performance: all images have loading="lazy" decoding="async" fetchpriority="low", preconnect to i.scdn.co. Commit: `319e533`. |
| 2026-07-31 | **STEPS 5-7: RESPONSIVE PASS, PERFORMANCE PASS, WIP BADGE REMOVED.** Responsive: mobile breakpoints verified (320px–768px), timeline/card padding tightened at ≤480px. Accessibility: accent-red improved to #ff3333 (4.75:1 contrast ratio, WCAG AA). Performance: meta description added (bilingual), SVG favicon (🔥), preconnect hints verified (fonts + Spotify CDN). WIP badge: status-badge HTML + CSS removed, title updated to drop "(Aan Die Bou)". Commit: `6ab7a98`. |
