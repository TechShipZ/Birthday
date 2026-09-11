# Priya's Party Notice 🎂

A birthday page for my sister. It opens as a locked envelope, wishes her,
and then serves her an official *Party Demand Notice* whose **NAHI** button
refuses to be caught.

**Live:** https://<username>.github.io/<repo>/

## How it goes

1. **Lifafa** — a brass padlock on a sealed envelope. Tap to open.
2. **Wish** — her photo, the wish, a note, and five candles to blow out.
3. **Thank you** — she says thanks; bhai has a follow-up request.
4. **The Notice** — `HAAN` or `NAHI`. `NAHI` runs away and never stops.
   Angry memes slam in, the *Bhai ka Sabar* meter drains to zero and then
   flips into *Bhai ka Gussa*. The only way out is `HAAN`.
5. **Celebration** — confetti, a code-generated fanfare, a party contract
   she signs, and a photo wall.

## Running it

It is one static page. Open `index.html`, or serve the folder:

```bash
python -m http.server 8899
```

## Publishing to GitHub Pages

```bash
git remote add origin https://github.com/<username>/<repo>.git
git branch -M main
git push -u origin main
```

Then **Settings → Pages → Source: `main` / `root`**. Live in about a minute.

> Heads up: GitHub Pages needs a **public** repo on a free account, and that
> makes everything in `assets/` — including the photos — publicly reachable.
> If you'd rather not, host it somewhere private instead (Netlify Drop,
> Vercel, or the Claude artifact link).

## Layout

```
index.html          the whole page — HTML, CSS and JS, no build step
assets/pics/        photos
assets/memes/       meme images
```

Fonts come from Google Fonts. Everything else is local. Confetti is drawn on
a `<canvas>` from scratch and the fanfare is synthesised with the Web Audio
API, so there are no media files to load.

## Editing it

- **The wish and the note** — `<section id="s-wish">`
- **Meme cards and their captions** — the `ANGRY` array in the script
- **Taunts while she's chasing the button** — the `TAUNTS` object
- **Contract clauses** — `<div class="contract">`
- **Hero photo** — the `<img>` inside `.frame`; swap in any file from `assets/pics/`
