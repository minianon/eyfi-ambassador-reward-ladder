# EYFI — Design System & Brand Guide

Brand guide for the **EYFI (Earn Your First Income) Challenge** and its **Campus Ambassador**
program. Reverse-engineered from the live production sites (`eyfichallenge.com`,
`ambassador.eyfichallenge.com`). Anything built for EYFI should look like it belongs on those
sites. Their stack is **Tailwind v4 + shadcn/ui** (oklch tokens, lucide icons, radix).

## Brand personality
Gen-Z, high-energy, "earned not handed", playful but credible. Dark stage, one loud lime accent,
money/hustle motifs (₹ coins, prizes), student-first voice. Think a game HUD meets a startup launch.

## Color tokens
Use as CSS custom properties. oklch values are taken verbatim from production.

| Token | Value | Use |
|---|---|---|
| `--bg` | `oklch(17% .005 250)` | page background (near-black, cool) |
| `--card` | `oklch(18% 0 0)` | card base |
| `--surface` | `oklch(22% .005 250)` | raised surface |
| `--fg` | `oklch(98% 0 0)` | primary text (near-white) |
| `--muted-fg` | `oklch(80% 0 0)` | secondary text |
| `--para` | `#C8C8C4` | body paragraphs |
| `--faint` | `#8A8A85` | captions / meta |
| `--lime` / `--primary` | `oklch(90% .22 125)` = `#C4F62E` | **hero accent, CTAs, highlights** |
| `--lime-fg` | `oklch(14% 0 0)` | text on lime (black) |
| `--orange` | `#FF5A1F` | marquee bar, logo, secondary accent |
| `--gold` | `#E8B923` | italic-serif accent lines |
| `--border` | `rgba(255,255,255,.12)` | hairline borders |

**One loud accent rule:** lime is the star. Orange and gold are supporting — never let them
compete with lime for the primary action.

### Signature gradients / textures
```css
/* dot-grid page texture (tile ~22px) over --bg */
background-image: radial-gradient(circle, rgba(255,255,255,.1) 1.2px, transparent 1.4px);
background-size: 22px 22px;

/* 3D lime coin/sphere */
radial-gradient(circle at 70% 25%, #F4FFB8 0%, #DFF864 30%, #A9D91A 65%, #6E8E10 100%);
/* 3D gold coin/sphere */
radial-gradient(circle at 32% 28%, #FFF6D0 0%, #FFDE6E 30%, #F0AC1F 65%, #C9820D 100%);
/* dark card */
linear-gradient(155deg, #2A2A2A, #141414);
```

## Typography (Google Fonts)
```
Bricolage Grotesque : 700, 800   — display & headings (tight tracking -0.01…-0.03em; hero often UPPERCASE)
Space Grotesk       : 400,500,700 — body, UI, pill CTA labels
Instrument Serif    : 400 + italic — emotive accent lines, colored lime or gold
Open Sans           : 600,700     — small nav items / labels
```
Pattern: bold sans headline with **one word swapped to Instrument Serif italic in lime/gold**
("build EYFI on your **campus**", "Why shouldn't it be **you?**").

## Components
- **Marquee ticker** — full-width `--orange` bar, black UPPERCASE Bricolage 800, `✦` separators, scrolls infinitely (`eyfi-marquee`).
- **Primary pill CTA** — `background:var(--lime)`, black text, `border-radius:999px`, Space Grotesk 700/800, padding ~16px 40px, **chunky pressable shadow**:
  `box-shadow: #5E7D14 0 6px 0 0, rgba(0,0,0,.6) 0 12px 24px -8px;` — on `:hover` translateY(3px) and shrink the 6px offset to feel pressed.
- **Outline pill** — transparent bg, `1px solid var(--lime)`, lime text (gold variant also used).
- **Card** — `linear-gradient(155deg,#2A2A2A,#141414)`, `1px solid var(--border)`, `border-radius:16px`.
- **3D coin** — disc using the lime/gold sphere gradient, stamped `₹`, floats (`eyfi-float`) + slowly spins (`eyfi-sphere-spin`). Used as ambient decoration, scattered.
- **Brush highlight** — black text over a rough lime marker swash (inline SVG) for one emphasized word.
- **Logo** — "EYFI" wordmark (lime "EYF" + orange "I" with a spark). Asset in repo/embedded.

## Motion
```css
@keyframes eyfi-float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }
@keyframes eyfi-sphere-spin { to { transform: rotateY(360deg) } }
@keyframes eyfi-marquee { to { transform: translateX(-50%) } }
```
Default transition `0.15s cubic-bezier(.4,0,.2,1)`. Always honor `prefers-reduced-motion: reduce`
(disable float/spin/confetti). Motion should feel springy and celebratory, never busy.

## Voice
Short, punchy, second-person. Examples from production: "Earned, not handed.", "Real scouts, real
campuses.", "You bring the twist.", "Someone is going to build EYFI on your campus. Why shouldn't it
be you?" Footer: "An initiative by Polygnan."

## Don'ts
- No light/cream backgrounds as the default (dark is the brand). No system-font fallbacks — load the
  four Google Fonts. No emoji as primary iconography. Don't introduce new accent hues — lime leads,
  orange/gold support. Keep the dot-grid subtle, never a flat black void.
