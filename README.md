# 💍 Annapoorna & Hitesh — Engagement Invitation

A mobile-first, single-page engagement invitation website.
**Sunday, 22 Nov 2026 · 11:00 AM · Sri Ghanchi Samaj, Bengaluru**

## Run locally

No build step and no dependencies. Any one of these works:

```bash
# Option 1 – Node (recommended)
npm start                 # → http://localhost:5500

# Option 2 – Python
python3 -m http.server 5500
```

Open **http://localhost:5500**. To preview on your phone, connect it to the same Wi-Fi and open `http://<your-computer-IP>:5500`.

## Features

- Envelope intro with wax seal — tap to open (this also starts the music)
- Background music: YouTube clip 0:46–1:08 with fade in/out, offline fallbacks
- Floating music button to pause / play
- Falling rose petals, scroll-reveal animations
- Live countdown to the ceremony
- Date / Time / Venue cards, Google Maps directions + embedded map
- Add to Calendar (Google Calendar or .ics for Apple / Outlook)
- Fully responsive (tested 360px → desktop), respects "reduce motion"

## Music

When the guest taps the envelope, the song is streamed from YouTube
(`https://www.youtube.com/watch?v=3s5XyooFGpg`) and only **0:46 → 1:08** plays, looping,
with a fade-in at the start and a fade-out at the end. Settings at the top of `js/main.js`:

- `YOUTUBE_ID`, `CLIP_START`, `CLIP_END` – which video and which part
- `FADE_IN`, `FADE_OUT`, `MAX_VOLUME` – fade lengths (seconds) and loudness

Fallbacks if YouTube can't play: `assets/music.mp3` (if added) → built-in flute instrumental.
YouTube needs an internet connection.

## Edit details

- Text content: `index.html`
- Couple artwork: `assets/couple.jpg` (1400×900)
- Event date/time used by countdown & calendar: `EVENT` object at the top of `js/main.js`
- Colours & fonts: CSS variables at the top of `css/style.css`

## Deploying later (GitHub Pages)

Push this repo to GitHub → Settings → Pages → Deploy from branch `main` / root.

## Structure

```
index.html
css/style.css
js/main.js
assets/            couple.jpg, floral corners, original card, (optional) music.mp3
server.js          zero-dependency local server
```
