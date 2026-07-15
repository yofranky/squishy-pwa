# Squishy — Stack & Squish! 🫧

A colorful jelly-bubble stacking game — Blocky's engine, restyled — built as an installable
Progressive Web App (PWA). Made by **BKAOS**.

**[▶️ Play it live](#)** — *(add your GitHub Pages link here once deployed)*

## What it is

Same core mechanics as Blocky (grid, gravity, line clears, 7 color palettes, Shape KAOS
difficulty decks, full accessibility panel), with one deliberate visual swap: every falling
and locked piece is a soft jelly bubble instead of a square block.

- Each bubble has a pair of eyes (white sclera, black pupil, no mouth) that track wherever
  you're touching the screen — before you touch, they default to looking up
- Every bubble has a continuous idle squash/stretch "dance" wobble, plus an extra squash
  bounce right when a piece lands
- Reduce Motion turns the wobble/bounce off but keeps the eye-tracking, so it stays accessible
- Colorblind-safe palette, high contrast, large UI, sound, and haptics — all independently
  toggleable, same as Blocky

## Why it's built this way

This is a BKAOS project, so:
- **Zero network calls.** No analytics, no ad SDKs, no font CDNs, no accounts. Built clean
  from the start — no CDN font dependency ever existed here, unlike Blocky's original build.
- **Installable, not app-store-gated.** It's a PWA: open the link, "Add to Home Screen" on
  iOS or Android, and it runs full-screen like a native app, offline, with its own icon.

## Tech stack

Vanilla HTML/CSS/JS, `<canvas>` for rendering, Web Audio API for sound, the Vibration API for
haptics, a hand-written service worker for offline caching. No frameworks, no build step,
no dependencies.

## Running it locally

```bash
npx serve .
# then open the printed localhost URL
```
Opening `index.html` directly via `file://` works for gameplay, but the service worker
(offline support / installability) needs `http(s)://` — a browser security rule, not a bug.

## Deploying (GitHub Pages)

1. Push this folder to a GitHub repo.
2. Repo Settings → Pages → deploy from the `main` branch, root folder.
3. Live URL: `https://<username>.github.io/<repo>/`.
4. Visit on your phone → browser menu → "Add to Home Screen".

## What I learned building this

- Reworking a shared rendering function (`drawBlock`) to swap an entire visual identity
  (squares → jelly bubbles with faces) while leaving every underlying game system —
  collision, scoring, line-clear logic — completely untouched.
- Converting screen-space touch coordinates into canvas-internal pixel coordinates so
  in-game eyes can accurately track a finger regardless of CSS scaling or device pixel ratio.
- Using a stable per-cell pseudo-random phase (derived from grid x/y) so every bubble's idle
  animation looks independent rather than obviously synchronized.
- Reusing the exact PWA conversion process (manifest, icons, service worker) across three
  separate games, proving it's a repeatable studio process and not a one-off.

## Project status

See `FUTURE_IDEAS.md` for parked feature ideas. This build is intentionally scoped to be
**finished** — playable, installable, documented — before anything new gets added.

---
*Squishy is made by BKAOS.*
