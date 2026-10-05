# Punch-in Monica

A tiny browser-based synth, built as a birthday gift for my cousin.

Punch-in Monica runs on top of [Strudel](https://strudel.cc), the live-coding music environment. Instead of typing patterns, you "punch in" numbers on a compact hardware-style panel, press play, and hear (and see) the result.

## How it works

The panel has two **note banks**: Bank 1 has 6 slots and Bank 2 has 4 slots. Each slot holds a note number (1–99), which Strudel plays as a MIDI note (60 = middle C). Press **play** and the panel turns your settings into a Strudel pattern and evaluates it live. The two banks play at the same time, layered on top of each other.

### Note slots

- **`+`** steps a slot through: `X` (off) → `-` (rest) → `1` → `2` → … → `99` → back to `X`.
- **Clicking the note itself** resets the slot to `X`.
- `X` slots are skipped entirely, and `-` slots are silent rests.

### Controls

| Button | What it does | Range |
|--------|--------------|-------|
| **A** | Attack | 0 – 5 (steps of 0.25) |
| **D** | Decay | 0 – 3 (steps of 0.25) |
| **S** | Sustain | 0 – 1 (steps of 0.05) |
| **R** | Release | 0 – 5 (steps of 0.1) |
| **W** | Waveform | `sawtooth`, `square`, `triangle`, `sine` |
| **FX** | Effect | `echo1`, `echo2`, `crush`, `clean` |
| **C** | Tempo (cycles per minute) | 10 – 120 |
| **SL** | Slows a bank down by that factor | 1 – 10 (per bank) |
| **↑** | Play (re-press to apply changes) | |
| **p** | Stop | |
| **F** | Toggle fullscreen | |
| **?** | Discover! | |

The **IN / OUT** lights show whether you're editing or listening, and the counter at the bottom counts the seconds since you pressed play.

Every sound also goes through a low-pass filter, is spread across the stereo field with a reversed copy (`jux(rev)`), and is drawn as a live spectrum.

## Built with

- JavaScript + [jQuery](https://jquery.com)
- [Strudel](https://strudel.cc) (`@strudel/web`)
- HTML + CSS

## Getting started

No build step or install needed.

1. Clone the repo:
```bash
   git clone https://github.com/AHeraldOfTheNewAge/Punch-in-Monica.git
```
2. Open `index.html` in your browser.

An internet connection is required, since Strudel and jQuery load from a CDN.

## Project structure

```
├── index.html      # Panel layout
├── css/style.css   # Styling
└── js/script.js    # Panel logic + Strudel pattern generation
```

## License

See [LICENSE.md](LICENSE.md).

---

Made with ♥ for Monica.
