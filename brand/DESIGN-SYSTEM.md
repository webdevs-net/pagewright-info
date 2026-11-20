# Pagewright design system

*Draft v0.1, 2026-11-20. Taken from what the live landing page
([`../index.html`](../index.html), webdevs-net.github.io/pagewright-info) already uses, so it
describes reality rather than a redesign. Tokens: [`pagewright-tokens.css`](pagewright-tokens.css).
Brand and voice: [BRAND.md](BRAND.md).*

## Feel

Warm paper, deep green ink, one warm orange for "attention". Calm, editorial, human: a
serif for headlines (like a well-made page), a clean sans for everything else. The opposite
of a dashboard.

## Color

| Token | Hex | Use |
|---|---|---|
| `--pw-bg` | `#FAF7F2` | Page background (warm paper) |
| `--pw-surface` | `#FFFFFF` | Cards, chat panel, site previews |
| `--pw-ink` | `#1D2320` | Text |
| `--pw-muted` | `#5B625E` | Secondary text |
| `--pw-line` | `#E6E0D6` | Borders, dividers |
| `--pw-accent` | `#2F5D50` | Primary: buttons, owner's chat bubbles, step numbers, links |
| `--pw-accent-hover` | `#244A40` | Primary hover |
| `--pw-accent-ink` | `#FFFFFF` | Text on accent |
| `--pw-accent-soft` | `#E5EFE9` | Icon tiles, "good" cards, check marks |
| `--pw-warm` | `#C8743A` | Eyebrows, the **staging banner**, "attention" only |
| `--pw-ai-bubble` | `#F1EDE6` | The AI's chat bubbles |

**Rules:**
- **Green means "you're in control"** (your messages, go-live buttons).
- **Orange means "preview, not live yet"** (the staging banner, eyebrows). Never use orange for errors.
- **Contrast:** body text is `--pw-ink` on `--pw-bg` (about 15:1). `--pw-muted` on `--pw-bg` passes AA for body text.
  White on `--pw-warm` is about 3.3:1, so use it only for large or bold text (the banner), not body copy.

## Type

| Role | Font | Size / weight |
|---|---|---|
| Headlines (h1 to h3), step numbers, logo wordmark | **Fraunces** (variable, opsz 9–144) | 600; h1 `clamp(2.3rem, 5vw, 3.6rem)`, h2 `clamp(1.8rem, 3.5vw, 2.5rem)`, h3 1.2rem |
| Body, UI, buttons | **Inter** | 400 / 500 / 600; body 17px / 1.6 |
| Eyebrow | Inter | 0.8rem, 600, uppercase, +0.12em tracking, `--pw-warm` |

Both are OFL Google Fonts. Self-host them instead of linking Google.

## Shape and space

- **Radius:** `--pw-radius` 14px on cards, the chat panel and tiles; 999px on buttons and tags; 8–10px on small icon tiles.
- **Content width:** 1120px max, 24px gutters.
- **Section padding:** 88px vertical.
- **Shadow** (floating panels only): `0 20px 50px -20px rgba(29, 35, 32, .25)`.

## Components

- **Buttons:** pill-shaped. Primary is an accent fill with white text that lifts 1px on hover. Ghost is accent text that underlines on hover.
- **Chat panel:** the signature component.
  - A white surface with a 1px line border and the floating shadow.
  - A small header with a green status dot.
  - Owner bubbles: accent green, right-aligned, bottom-right corner squared.
  - AI bubbles: `--pw-ai-bubble`, left-aligned, bottom-left corner squared; any link in them is accent, weight 500.
  - Bubbles pop in one after another, and appear at once with Reduce Motion.
- **Site preview card:** browser-dot bar, the orange **staging banner** ("STAGING PREVIEW", 0.65rem caps), then the page. It always sits next to or overlapping the chat, so the cause and the effect are seen together.
- **Cards:** `--pw-bg` on surface sections. A "good" card (the Pagewright option in comparisons) uses `--pw-accent-soft` with a green tag.
- **Feature tiles:** a 40px soft-green icon tile with a 1.8px-stroke line icon in accent, then title and short text.
- **Checklist (safety):** a 30px soft-green circle with an accent check, a bold label, and a muted explanation.
- **Steps:** numbered 42px accent circles in Fraunces.

## Imagery

- Visuals show **the request and the result together**.
- Use fictional example businesses with warm, real-world photography.
- Label mock-ups "Illustration".
- No Claude, ChatGPT, Anthropic or OpenAI logos or app chrome.

## Logo

**Not decided.** The landing page uses a placeholder: the word "Pagewright" in Fraunces next
to a green tile with a white "P". Proposals are in [`logo-proposals/`](logo-proposals/), and
none is approved.
