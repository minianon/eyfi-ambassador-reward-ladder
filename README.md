# EYFI Campus Ambassador — Reward Ladder 🪜

An interactive, gamified **reward ladder** for the [EYFI (Earn Your First Income) Challenge](https://eyfichallenge.com/)
Campus Ambassador program. Built as an assignment for Polygnan.

**▶ Live demo:** https://claude.ai/code/artifact/6f275c83-7c2b-42e9-b872-b741ac50a9c8

![Demo of The Climb reward ladder](reward-ladder-demo.gif)

## "The Climb"

An ambassador's registration count drives a draggable slider (**0 → 200+**). As you climb:

- an avatar rises up a gradient rail,
- each tier flips **locked → current → unlocked**,
- the rank badge, live counter and progress bar update in real time,
- crossing a milestone fires a **₹-coin confetti burst**.

There's also an **Auto-climb** button that plays the whole journey. The page is a single
self-contained HTML file — mobile-first, keyboard-accessible, theme-aware (light/dark), and
respects `prefers-reduced-motion`.

## Tiers

| Milestone | Rank | Unlocks |
|---|---|---|
| Selected as Scout | Scout | Private community access · Starter kit |
| 25 registrations | Campus Ambassador | Official CA title · First swag drop · Prize-linked challenge |
| 50+ registrations | Igniter | Campus event grants · Exclusive merch |
| 75+ registrations | Trailblazer | Mentorship access · Campus event grants |
| 100+ registrations | Powerhouse | Paid internship · Ambassador events invite |
| 200+ registrations | Founding Circle | Founding Team consideration |

## Files

- [`reward-ladder.html`](reward-ladder.html) — the interactive page (open in any browser)
- [`reward-ladder-demo.gif`](reward-ladder-demo.gif) / [`reward-ladder-demo.webm`](reward-ladder-demo.webm) — ~7s demo clip
- [`SUBMISSION.md`](SUBMISSION.md) — assignment note (tools & approach)

## Built with

Vanilla HTML/CSS/JS (no frameworks, no external assets — confetti is a `<canvas>` particle system).
Demo recorded headlessly with Playwright and assembled into a GIF with Python/Pillow.
