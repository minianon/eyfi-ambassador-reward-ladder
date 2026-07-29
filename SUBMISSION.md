# EYFI Campus Ambassador — Reward Ladder ("The Climb")

**Assignment:** Design the reward ladder for the EYFI Campus Ambassador program in a way
that's interactive and appealing to college students.

## What I built
An interactive, gamified reward ladder called **"The Climb."** The ambassador's registration
count drives a draggable slider (0 → 200+). As you climb, an avatar rises up a gradient rail,
each tier flips from locked → current → unlocked, the rank badge and live counter update, and
crossing a milestone fires a ₹-coin confetti burst. There's also an **Auto-climb** button that
plays the whole journey. It's mobile-first, keyboard-accessible, respects reduced-motion, and
works in light and dark themes.

**The six tiers** (faithful to the brief): Scout → Campus Ambassador (25) → Igniter (50+) →
Trailblazer (75+) → Powerhouse (100+) → Founding Circle (200+).

## Tools & how I did it
Built as a single self-contained HTML/CSS/JS file (no frameworks or external assets — confetti
is a `<canvas>` particle system, ₹ motifs and rank glyphs inline) using **Claude Code**, with the
palette and voice matched to the live EYFI + ambassador sites (orange-led, lime + gold accents).
I rendered the demo headlessly with **Playwright** (Chromium) to record the climb, then assembled
the GIF with **Python/Pillow**.

## Files
- `reward-ladder.html` — the interactive page (open in any browser).
- `reward-ladder-demo.gif` / `reward-ladder-demo.webm` — the demo clip (~7s).
- Live version: https://claude.ai/code/artifact/6f275c83-7c2b-42e9-b872-b741ac50a9c8
