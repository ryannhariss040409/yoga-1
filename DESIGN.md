# Design

## Theme

Light only. Scene: a 55-year-old reading on an iPhone in a bright kitchen at 7am — daylight glare, reading glasses maybe not on yet. Pure white ground; all warmth lives in the brand color and photography, never in a cream background.

## Color (OKLCH only)

Strategy: **Committed** — deep oxblood red carries the identity (CTAs, testimonial drench band, final CTA band). Reference feel: "darkroom safelight" — vital, warm-blooded, adult. Deliberately NOT the sage-green/cream yoga cliché.

```css
--bg:            oklch(1 0 0);            /* pure white */
--surface:       oklch(0.955 0.008 10);   /* white pulled toward brand hue */
--ink:           oklch(0.24 0.02 10);     /* near-black, warm; ≥12:1 on bg */
--muted:         oklch(0.44 0.02 10);     /* secondary text; ≥5:1 on bg */
--primary:       oklch(0.47 0.17 10);     /* oxblood — white text always */
--primary-deep:  oklch(0.40 0.15 10);     /* hover / drench gradient end */
--accent:        oklch(0.85 0.13 85);     /* marigold — badges, stars; ink text */
--ink-surface:   oklch(0.17 0.015 10);    /* footer ground */
```

## Typography

- **Headings:** Besley (sturdy clarendon revival — the spine of a hardcover field guide). 700–800, tight-but-legal tracking (≥ -0.02em). Italic for pull-quotes.
- **Body:** Atkinson Hyperlegible — designed by the Braille Institute for low-vision readers; the accessibility choice IS the brand choice for a 45+ audience.
- Base 19px, line-height 1.65, body measure ≤ 68ch. Scale ratio ~1.3.

## Layout & Motion

- Max width 1120px; fluid section spacing `clamp(4rem, 10vw, 7.5rem)`.
- Photo-led: split hero (portrait photo right), alternating image/copy rows for class tracks, full-width drench bands for testimonials and final CTA.
- Motion: one gentle fade-up per section via IntersectionObserver, JS-gated (`.js`) with a 2s failsafe; fully disabled under `prefers-reduced-motion`. No parallax, no stagger circus.
- iOS: safe-area padding, 48px+ targets, mobile sticky bottom CTA bar after hero scrolls away, native `<details>` FAQ.

## Components

- Buttons: pill-shaped, 52px min height, Besley 700 label, oxblood fill/white text (primary) or 2px ink outline (secondary).
- Testimonial band: oxblood drench, Besley italic quotes in white, marigold stars.
- Pricing: one wide panel, two plans side by side inside it, plain-talk fine print in body size (not 12px legalese).

## Imagery

Pexels photography of real adults 55–70, daylight, mid-practice. Never youth-fitness stock, never frailty framing. Alt text written in brand voice. Files in `/images`.
