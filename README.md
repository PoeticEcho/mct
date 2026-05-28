# MCT — Math Chiptune Tracker

**MCT (Math Chiptune Tracker)** is a browser-based 8-bit loop maker and chiptune composition assistant.

It helps you generate, compare, lock, fix, and export chiptune-style background music using mathematical generation, tracker-style editing, and Web Audio synthesis.

> Find a good loop → keep the good parts → fix the weak parts → compare versions → export a tiny Web Audio background music player.

Current status: **Public Beta**

---

## Live Demo

If you publish this project with GitHub Pages, add your live demo link here:

```text
https://YOUR_USERNAME.github.io/math-chiptune-tracker/
```

---

## What MCT Does

MCT is not a full DAW.  
It is a small creative coding tool for making tiny 8-bit loops directly in the browser.

The workflow is organized into five stages:

```text
Find → Keep → Fix → Compare → Finish
```

### 1. Find

Generate loop ideas with:

- mood presets
- seed-based generation
- mathematical melody rules
- chord progression presets
- motif-based generation
- song structures with build-up and peak sections
- `Generate 20 Takes` with Best 3 recommendation

### 2. Keep

Preserve what works:

- Favorite Takes
- Checkpoints
- A/B Compare slots
- channel locks:
  - Lead
  - Bass
  - Arp
  - Drum

Locked channels are preserved when regenerating weak sections.

### 3. Fix

Improve only the weak parts:

- re-roll unlocked channels only
- auto-fix weakest section
- Composer Review Card
- Melody / Loop / Groove scoring
- Point Control:
  - boost current step
  - soften current step
  - boost current pattern
  - soften current pattern
- Director Buttons:
  - make it cuter
  - less noisy
  - stronger melody
  - reduce drums
  - build up the ending
  - smooth loop ending

### 4. Compare

Choose better versions:

- A/B playback
- A/B select
- Favorite to B slot
- Undo / Redo / Checkpoint floating bar

### 5. Finish

Export the result:

- `.mct` project file
- Base64 MCT data
- tiny HTML background music player
- OGG/WebM loop recording where supported

---

## Features

- Single-file browser app
- No build step required
- Web Audio synthesis
- Custom `.mct` JSON-based format
- Tracker-style 4-channel pattern grid
- Safe Grid Editing:
  - single click: select
  - double click: edit
  - right click: clear
- Lead / Bass / Arp / Drum channels
- Favorite Takes
- A/B Compare
- Channel Lock
- Composer Review Card
- Melody / Loop / Groove Score
- Director Buttons
- Point Control
- Section Timeline
- MP3 Analysis Report
- Tiny HTML Player Export

---

## Mood Presets

MCT includes several mood presets:

- cute game BGM
- tension
- space
- volcano
- laboratory
- happy
- sad
- anger
- running

Each preset adjusts musical parameters such as BPM, scale, drum style, chord progression, structure, density, and variation.

---

## Mathematical Generation

MCT can generate patterns using:

- random walk melody
- sine-wave contour
- Euclidean rhythm
- cellular automata

These rules are combined with musical constraints such as scale, chord progression, motif, density, velocity, note length, and song structure.

---

## Instrument Presets

### Lead

- Soft Square
- Bright Square
- Pulse Lead
- Tiny Bell
- Laser Lead

### Bass

- Triangle Bass
- Square Bass
- Pluck Bass
- Sub Bass

### Arp

- Thin Arp
- Sparkle Arp
- Bell Arp

### Drum Kits

- Classic Kit
- Cute Kit
- Hard Kit
- Noise Kit

The exported HTML player attempts to reproduce the selected instrument presets and drum kit.

---

## MP3 to MCT Approximation

MCT includes an experimental **MP3 → MCT approximation** feature.

It can analyze up to **150 seconds** of an MP3 file and estimate:

- BPM
- pitch confidence
- drum detection
- loop match
- lead / bass / arp / drum patterns

This works best with simple 8-bit or chiptune-style audio.

Important limitations:

- This is **not** a perfect audio-to-MIDI converter.
- This is **not** a stem-separation tool.
- Complex full-mix audio, vocals, reverb-heavy tracks, and commercial songs may produce poor results.
- Do not import, transform, or redistribute copyrighted MP3 files unless you have the right to do so.

MP3 processing is performed locally in the browser.

---

## Quick Start

No build process is required.

1. Clone or download this repository.
2. Open `index.html` in a modern browser.
3. Click **좋은 루프 찾기** or **Generate 20 Takes**.
4. Save good ideas as Favorites.
5. Use A/B Compare and channel locks.
6. Export as `.mct`, `.ogg/.webm`, or a tiny HTML player.

```bash
git clone https://github.com/YOUR_USERNAME/math-chiptune-tracker.git
cd math-chiptune-tracker
```

Open:

```text
index.html
```

Or run a local server:

```bash
python -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

---

## Browser Support

Recommended browsers:

- Chrome / Edge
- Firefox
- Safari

Required browser APIs:

- Web Audio API
- File API
- MediaRecorder API for recording
- Clipboard API, with fallback when blocked
- Audio decoding support for MP3 import

Notes:

- Audio playback requires a user click because of browser autoplay policies.
- OGG recording depends on browser support. Some browsers will export WebM instead.
- MP3 decoding depends on browser codec support.
- Clipboard access may be blocked in some embedded or sandboxed environments. MCT falls back to selecting the text for manual copy.

---

## MCT File Format

`.mct` is a JSON-based project format.

It stores musical instructions, not raw audio:

- format version
- created date
- mood
- BPM
- root / scale
- formula
- drum pattern
- chord progression
- song structure
- motif mode
- note length preset
- velocity preset
- swing / humanize
- instrument presets
- motif data
- channel locks
- density / variation
- seed
- pattern data
- compare slots
- favorites

Because `.mct` stores instructions instead of audio, it is small and easy to embed.

---

## Exported HTML Player

MCT can export a tiny HTML background music player.

The exported player uses:

- Web Audio synthesis
- Base64-encoded MCT data
- a small floating play button
- no external audio files

This is useful for:

- browser games
- educational simulations
- small web experiments
- single-file HTML prototypes

The exported player attempts to match the main app’s instrument presets and drum kits.  
Exact sound may vary slightly between browsers.

---

## Public Release Checklist

Before publishing on GitHub, verify:

- [ ] `index.html` opens with zero `SyntaxError` in the browser console
- [ ] Play / Stop works
- [ ] Generate Song works
- [ ] Generate 20 Takes works
- [ ] Best Take apply works
- [ ] Favorite save / apply / delete works
- [ ] A/B Compare works
- [ ] Undo / Redo / Checkpoint works
- [ ] Lead / Bass / Arp / Drum Lock works
- [ ] Re-roll unlocked channels works
- [ ] Director Buttons work
- [ ] Point Control works
- [ ] `.mct` export works
- [ ] `.mct` import works
- [ ] HTML Player Export works
- [ ] Copied HTML Player runs in a blank HTML file
- [ ] OGG or WebM recording works in at least one browser
- [ ] MP3 import clearly states that conversion is approximate
- [ ] README.md is included
- [ ] LICENSE is included
- [ ] No copyrighted MP3/audio files are committed

---

## Suggested Repository Structure

```text
math-chiptune-tracker/
├─ index.html
├─ README.md
├─ LICENSE
├─ PUBLISH_CHECKLIST.md
└─ docs/
   └─ github-pages.md
```

---

## GitHub Pages

This project can be deployed directly with GitHub Pages.

1. Push `index.html`, `README.md`, and `LICENSE` to the repository.
2. Open GitHub repository settings.
3. Go to **Pages**.
4. Select:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. Save.

Your demo URL will look like:

```text
https://YOUR_USERNAME.github.io/math-chiptune-tracker/
```

---

## Roadmap

Potential future improvements:

- modular JavaScript refactor
- better mobile layout
- keyboard shortcuts
- pattern copy / paste
- MIDI export
- WAV rendering
- more accurate key and scale detection
- more robust MP3 analysis
- preset library
- shareable URL state
- separate automated tests
- better documentation for `.mct` internals
- optional build/test pipeline

---

## Known Limitations

MCT is currently a public beta / experimental prototype.

Known limitations:

- MP3-to-MCT conversion is approximate.
- Generated music quality varies by seed and settings.
- Full commercial music separation is not supported.
- Some browsers may block clipboard access.
- OGG export is browser-dependent.
- Long MP3 imports may be slower on low-end devices.
- The current app is a single HTML file and should eventually be modularized.

---

## License

Recommended license: **MIT License**

Suggested project policy:

- MCT source code: MIT
- Generated `.mct` files: owned by the user who created them
- Exported music: owned by the user who created it, subject to any imported source material rights
- Imported MP3 files: users are responsible for having the proper rights

---

## Status

Current status: **Public Beta**

MCT is suitable for GitHub release as an experimental creative coding project, as long as MP3 import is clearly described as approximate and no copyrighted audio files are included in the repository.
