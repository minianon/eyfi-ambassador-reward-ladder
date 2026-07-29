# EYFI Campus Ambassador — Reward Ladder

**Assignment:** Design the reward ladder for the EYFI Campus Ambassador program in a way that's
interactive and appealing to college students.

## What I built
An interactive reward ladder where dragging a slider (or hitting **Auto-climb**) grows your
registration count — the live counter and rank update, a progress spine fills, each of the six tiers
flips locked → current → unlocked, and every milestone fires a ₹-coin confetti burst. It's rebuilt to
look like a real slice of the live ambassador site: orange ✦ marquee, dark dot-grid, lime `#C4F62E`
accent, floating 3D ₹ coins, and their exact fonts (Bricolage Grotesque / Space Grotesk / Instrument
Serif). Mobile-first, keyboard-accessible, and reduced-motion aware.

## Tools & how I did it
I used **Claude Code** to reverse-engineer the production design system (colors, fonts, animations,
coin motifs) from `eyfichallenge.com` + `ambassador.eyfichallenge.com` with a headless **Playwright**
browser, captured it in a `CLAUDE.md` brand guide, then hand-built the ladder as one self-contained
HTML/CSS/JS file (no frameworks) styled with their tokens. The demo clip was recorded headlessly with
Playwright and assembled into a GIF with **Python/Pillow**.

## Links & files
- Live: https://tusharbhardwa.github.io/eyfi-ambassador-reward-ladder/
- `reward-ladder.html` / `index.html` — the page
- `reward-ladder-demo.gif` / `.webm` — the ~7s demo clip
- `CLAUDE.md` — the extracted EYFI design system
