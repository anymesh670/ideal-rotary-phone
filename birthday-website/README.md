# 🎂 Happy Birthday — Farhan Ur Rehman, CA

A premium, single-file, black & gold **Chartered Accountant**-themed
birthday website. Pure HTML/CSS/JavaScript, no backend, no build step.

## This version is fully self-contained

**Everything — the HTML, all CSS, all JavaScript, your 6 photos, and your
`music.mp3` — is baked directly into the one `index.html` file.** Nothing
is loaded from `assets/` or `photos/` at runtime anymore.

This was done specifically to fix the "works on laptop, not on
phone/iPhone" problem: many mobile browsers (especially Safari on iPhone)
refuse to let a locally-opened HTML file read *other* files sitting next to
it, even if they're named and placed correctly. By embedding your photos
and song straight into `index.html` as data, there's nothing left for the
phone to "refuse to read" — the moment the page opens, everything it needs
is already inside it.

The `assets/` and `photos/` folders are still included in this download
for your reference (so you always have your original files), but the site
itself no longer needs them to be present.

## How to run it

1. Copy `index.html` anywhere — phone, tablet, or computer. (You technically
   only need this one file now.)
2. Open it directly in any browser (tap/double-click it).
3. Photos, music, and every animation will load immediately — no separate
   files to lose, no folder structure required.

> The file is large (~9 MB) because your photos and song are embedded
> inside it as data — that's expected and is what makes it self-sufficient.
> It may take a second longer to open than a normal web page, especially
> on an older phone, but it will not depend on any other file once it's
> loaded.

## About the microphone ("Blow The Candles")

This is the one feature mobile browsers restrict for security reasons no
matter what: **microphone access is only allowed on `https://` or
`localhost` pages**, never on a file opened straight from phone storage
(`file://`). This is a rule enforced by the phone's operating system and
browser, not something any code change can get around.

- On a laptop, some browsers (like Edge) are more lenient with `file://`
  pages and may allow it — which is why it worked there.
- On a phone opened as a local file, the mic prompt usually won't appear,
  and the site automatically falls back to **"tap the button again to blow
  the candles out manually"** — so nothing breaks, it just skips the real
  blow-detection.

### To get the real microphone feature working on every phone too
Host the file for free, in about a minute:
1. Go to **https://app.netlify.com/drop**
2. Drag `index.html` (just this one file) onto the page.
3. You'll get a real `https://something.netlify.app` link.
4. Open that link on any Android, iPhone, tablet, or laptop — the
   microphone-based candle blowing will now work identically everywhere,
   because it's a secure `https://` page.

(GitHub Pages, Vercel, or any static host works exactly the same way.)

## Editing your content

Because everything now lives inside `index.html`, edits are made in that
one file, using any text/code editor:

- **Photos** — search for `EMBEDDED_PHOTOS` — each photo is one long
  `"data:image/...;base64,...."` string in a list. To swap a photo, it's
  easiest to ask for the file to be regenerated with your new images rather
  than hand-editing base64 text.
- **Music** — search for `id="bgMusic"` — the `src="data:audio/mpeg;base64,...."`
  is your song. Same as above: easiest to regenerate rather than hand-edit.
- **Names/text** — search for `Farhan Ur Rehman` (landing/hero), `data-full=`
  on `#typewriterText` (the animated wish), or the `#finale` section (the
  closing message) — all plain, editable text.
- **Colors** — search for `:root{` near the top of the `<style>` block; every
  color used site-wide is defined once there.
- **Candle count / mic sensitivity** — search for `CANDLE_COUNT`,
  `BLOW_THRESHOLD`, and `BLOW_SUSTAIN_MS` near the top of the `<script>`
  block.

## Features included

- Cinematic loading sequence with a gold "CA" seal medallion
- Animated title reveal + Enter button, floating gold-dust particles, slow
  light beams
- Glassmorphism "certificate frame" motif reused across every section
- Full-screen automatic photo slideshow: fade + Ken Burns zoom, auto-advance
  every 4 seconds, previous/next arrows, dot navigation, fullscreen toggle,
  keyboard arrow-key support
- Typewriter-animated birthday message that plays when scrolled into view
- A layered CSS birthday cake with flickering candle flames
- Real microphone-based "blow the candles out" interaction (Web Audio API
  volume detection), with a manual-click fallback if the mic is unavailable
- Smoke animation, canvas confetti, canvas fireworks, floating balloons,
  floating hearts, all triggered together the moment the candles go out
- A small Web-Audio celebration chime (no external sound file required)
- Background music with mute/unmute toggle and an autoplay-blocked fallback
  "Play Music" button
- Fully responsive layout (phones, tablets, laptops, desktops)
- Keyboard-focus styles, `prefers-reduced-motion` support, smooth scrolling

## File structure

```
birthday-website/
├── index.html          # everything — structure, styles, scripts, photos, and music
├── assets/
│   └── music.mp3        # your original file, kept for reference only
├── photos/
│   └── photo1.jpeg … photo6.jpeg   # your originals, kept for reference only
└── README.md
```

Made with ❤️ for **Farhan Ur Rehman, CA**.
