# ORCHESTRATOR.md — fokofpolisiekar.com

**Maintained by:** HQ orchestrator chat (no dedicated project-orchestrator chat yet)
**Last updated:** 2026-07-29
**Purpose:** Master ledger for the fokofpolisiekar.com project — a single static landing page (WIP/coming-soon aesthetic) hosted on GitHub Pages. Tiny scope; HQ triages directly until the project grows enough to warrant its own orchestrator chat.

---

## §1 How This Works

- **HQ-owned directly.** No project-orchestrator chat or track chats opened yet. HQ reads and writes this ledger on its own syncs.
- **Ledger is a read-only index** at this scale — if a source doc disagrees with this file, the source doc wins and this file gets fixed.
- **When the project grows** (multiple pages, content tracks, automation), open a dedicated project-orchestrator chat on `C:\WildLogic\fokofpolisiekar\` and hand the ledger to it. That chat then owns this file and triages for its own tracks.
- **Routing DOWN (HQ → project):** HQ appends an `HQ NOTE — YYYY-MM-DD` section at the end of this file. The owning chat triages it on next sync.
- **Routing UP (project → HQ):** HQ reads this ledger's status board + maintenance log on its own syncs. Prefix `HQ:` in the maintenance log for urgent flags.

---

## §2 Track Status Board

| Track | Scope | State | Owner | Notes |
|---|---|---|---|---|
| Landing page | Single-file static WIP/coming-soon page for fokofpolisiekar.com | **WIP** | HQ | `index.html` — self-contained, punk/alt aesthetic, GitHub Pages deploy |

---

## §3 Activation Pipeline

| Step | Action | State | Notes |
|---|---|---|---|
| 1 | Build WIP landing page (`index.html`) | **IN PROGRESS** | Raw punk aesthetic, responsive, no JS |
| 2 | Set up GitHub repo | TODO | Repo name TBD (suggest: `fokofpolisiekar`) |
| 3 | Configure GitHub Pages | TODO | Serve from repo root or `docs/` — see `README.md` |
| 4 | Point domain DNS | TODO | fokofpolisiekar.com → GitHub Pages (A/CNAME records) |

---

## §4 Cross-Track Contracts — DO NOT BREAK

> No project-level contracts yet. Flag shared keys/gateways/schemas here BEFORE implementation as tracks emerge.

**Shared assets to be aware of (from HQ §4):**
- **WildLogic brand voice ("Wired Different")** — all projects use this per HQ §4 rulings. The fokofpolisiekar.com page carries a "A WildLogic project" footer line; brand voice applies to any future copy on this site.

---

## §5 Open Items

| Item | Status | Notes |
|---|---|---|
| Build WIP landing page | IN PROGRESS | `index.html` — single-file, inline CSS, punk aesthetic |
| Set up GitHub repo | TODO | Suggest name: `fokofpolisiekar` |
| Configure GitHub Pages | TODO | Decide: serve from root or `docs/` folder |
| Point domain DNS | TODO | fokofpolisiekar.com → GitHub Pages |
| Content direction for post-launch pages | PARKED | See §6 |

---

## §6 Backlog / Ideas

- Content direction TBD — the name references the famous SA alternative rock band; future content could explore music, culture, alt-scene content. No decisions yet.
- Post-launch: consider whether this stays a single-page stub or grows into a content site.
- WildLogic brand site (`wildlogic.co.za`) is a separate asset at HQ level — no cross-pollination planned yet.

---

## §7 Ledger Maintenance Log

| Date | Change |
|---|---|
| 2026-07-29 | Ledger created. Project seeded by HQ: folder `C:\WildLogic\fokofpolisiekar\`, single-track scope (WIP landing page for fokofpolisiekar.com). HQ-owned directly — no project-orchestrator chat yet. Activation pipeline seeded (build page → GitHub repo → GitHub Pages → DNS). Awaiting: GitHub repo setup, Pages config, domain DNS. |
