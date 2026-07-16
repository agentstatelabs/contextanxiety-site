# Context Anxiety

A single-page marketing site in the style of a 1980s TV infomercial,
designed to name and dramatize the phenomenon of **context anxiety** —
the low-grade dread of re-explaining your project to an AI tool every
morning. The site funnels to [CTXone](https://ctxone.com/) as the cure.

## What's in this directory

- `index.html` — the whole site. Single file, all CSS inline, no
  build step, no framework, no dependencies. Open it in a browser
  and it works.

That's it. The simplicity is deliberate: a weird little one-page
parody site should look and feel like a weird little one-page site,
not like a corporate marketing deployment.

## Structure

1. **Hero** — "CONTEXT ANXIETY" title with 80s drop-shadow treatment
2. **Hook** — "Does this look familiar?" with a recognizable scene
3. **Symptoms** — 10 numbered symptom cards, each with a scene and a
   punchline, escalating in absurdity
4. **Diagnosis** — the reveal: "You're suffering from context anxiety"
5. **Until-now despair** — grey, hopeless
6. **BUT WAIT…** — transition, zoom-pulse animation
7. **CTXone reveal** — product card with spinning "AS SEEN ON" starburst
8. **Offer stack** — checkmark feature list with "★ BONUS" rows
9. **Testimonials** — four fake-but-emotionally-accurate quotes
10. **Final CTA** — giant skewed install button linking to `ctxone.com`
11. **Disclaimers** — the tiny legal-ish fine print every commercial has
12. **Footer** — GitHub, docs, quickstart links

## Running locally

```bash
# Open it directly
open index.html

# Or serve it with any static server
python3 -m http.server 8000
# then visit http://localhost:8000/
```

Nothing to install. No build.

## Deploying

### Option A: GitHub Pages (simplest)

1. Push this directory to a GitHub repo as the root.
2. Repo settings → Pages → source: main branch, root directory.
3. Wait for the build (there's no build — GitHub just serves `index.html`).
4. Site is live at `https://<user>.github.io/context-anxiety/`.

If you want a custom domain like `contextanxiety.com`:

1. Add a `CNAME` file containing `contextanxiety.com` at the repo root.
2. Settings → Pages → custom domain.
3. DNS: point A records at GitHub Pages IPs (185.199.108–111.153) or
   CNAME `contextanxiety.com` → `<user>.github.io`.

### Option B: Cloudflare Pages, Netlify, Vercel

All three will serve `index.html` out of the root with zero config.
Drag-and-drop the directory into their dashboards.

### Option C: just host it anywhere

It's one HTML file. Any webserver will do. S3 + CloudFront, a VPS
with nginx, a bare `python3 -m http.server` on a box you own —
whatever's easiest.

## Tone and editing notes

- **Parody with a real edge.** Every joke has a kernel of recognizable
  pain underneath. If you edit a symptom, keep that balance —
  pure comedy without the pain underneath falls flat; pure pain
  without the comedy is a whiny blog post.
- **The target reader recognizes themselves in ≥3 symptoms.** If a
  symptom doesn't make a working developer go "oh no, that's me,"
  it's either too generic or too absurd. Cut it.
- **The funnel is the point.** Every section is a step toward the
  CTA. If you add content that doesn't move the reader closer to
  "install CTXone," ask whether it belongs.
- **Keep it one page.** If you find yourself wanting a second page,
  that's scope creep. Make the new content a new site instead.

## Design notes

All colors come from 80s infomercial language:

- Yellow (`#ffd700`) — primary background
- Red (`#ee1e1e`) — accents, CTAs, dramatic headings
- Black (`#000`) — borders, type
- Cream (`#fff8dc`) — card backgrounds for readability
- Green (`#22c55e`) — checkmarks in the offer stack (breaks the
  palette deliberately, because OxiClean uses green checkmarks)

Typography:
- Headlines: `Impact` / `Arial Black` for that punchy TV-title look
- Body: Georgia for the italic voice-over feel
- Monospace: Courier New for status bars and install commands

Visual effects:
- CRT scanlines: subtle repeating-linear-gradient overlay across the
  whole page
- Drop shadows: chunky black offsets for the "thick border" feel
- Skew transforms: tiny rotations (±0.6deg) on cards for off-kilter
  energy
- Animations: pulsing "REC" dot, flickering diagnosis pre-text,
  zoom on "BUT WAIT," spinning starburst

## Related

- CTXone project: https://github.com/ctxone/ctxone
- Context Anxiety concept doc: `docs/CONTEXT_ANXIETY.md` in the
  CTXone repo (this site's argument, written as a straight essay
  for people who want the non-parody version)
- CTXone landing page: https://ctxone.com/
