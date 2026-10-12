# Nashville Number System – Guitar Chords

An offline-first, single-file web app for learning and practicing the **Nashville Number System** on guitar.

Pick a key (all 12) and a mode (Major / Minor) and instantly see every *numbered chord* with a real fingerboard diagram, transpose famous progressions into any key, explore scales / modes / pentatonics on the fretboard, play 49 guitar licks, and practice with a built-in metronome.

Everything ships in one self-contained `index.html` — no install, no dependencies, no internet required once saved locally.

## Features

**Chords & progressions**
- 12 keys × Major/Minor — every chord of the key with an SVG fingerboard chart (standard tuning, low E on the left).
- Nashville notation: `1 4 5`, `2- 5 1`, `♭7`, `7°`, etc., with finger placement numbers.
- 17 famous progressions (major + minor), transposed live into your chosen key.
- Each progression lists the well-known songs that use it, their usual key, and a simplified strumming pattern.
- Audio: tap any chord card to hear it, or hit **▶** on a progression to play the whole loop with the current chord highlighted.

**Nashville table**
- The complete 12-keys × 7-degrees reference table in one view, following Major or Minor, with the current key highlighted.

**Scales, modes & pentatonics**
- Ionian, Dorian, Phrygian, Lydian, Mixolydian, Aeolian, Locrian, Major/Minor pentatonic and Blues scale.
- Whole-neck fretboard diagrams, note names or Nashville numbers, and single-position "boxes" starting on the root.
- Audio: click **Play** to hear the scale run ascending and descending.

**Licks**
- 49 playable licks across 7 styles: Blues, Country, Rock, Jazz, Funk, Folk, Metal.
- TAB + fretboard rendering with stepped playback and per-note highlighting.

**Metronome**
- Docked, always-available FAB with a compact panel (BPM stepper, accent dots, start/stop).
- Expandable "More" panel: BPM presets, slider + fine number input, tap tempo, volume, beat/bass sounds, Rock/Pop/Shuffle grooves, subdivisions (eighths, triplets, sixteenths), count-in and silent mode.
- Space bar toggles the metronome anywhere on the page.

**Mood themes & i18n**
- The accent color, light/dark theme and background tint follow the current key and Major/Minor — plus a text mood for each key (e.g. C major = *triumphant*).
- Fully bilingual: English / Русский.

## Getting started

The app is a single HTML file. Open it in any modern desktop or mobile browser:

```text
index.html
```

Or host it anywhere (GitHub Pages, Netlify, a USB stick, etc.) — no server-side code is required.

Settings (language, key, mode, metronome state, low-ink preferences) persist automatically in `localStorage`.

### Quick tour

| Area | What it does |
| --- | --- |
| Key + Major/Minor toolbar | Switch key / mode; the whole page (chords, progressions, scales, table, mood) re-renders |
| `?` button | What the numbers mean and how transposition works |
| Tabs | Chords & progressions / Scales, modes & pentatonics / Licks |
| Chord cards | Click any card to hear the chord |
| ▶ on a progression | Plays the chord loop and highlights each chord in turn |
| Beat dots | Tap a dot to toggle that beat's accent |
| ♩ FAB | Opens the metronome panel |

## How it works

- **Single file**: HTML, CSS and JavaScript in one `index.html`; no build step, no external libraries, no network requests.
- **Nashville engine**: chords are computed from scale degrees (`MODES`), so `1 4 5` is correct in all 12 keys. The table, progressions, scales and licks all derive from the same degree math.
- **Audio**: generated with the Web Audio API (oscillators + noise for hats/snares/kicks) — no audio assets.
- **Themes**: CSS custom properties + HSL hue derived from the selected key; follows `prefers-color-scheme`, with `prefers-reduced-motion` respected.

## Repository layout

```text
.
├── index.html   # the entire application
├── README.md
└── LICENSE
```

There is deliberately no scaffolding: the whole project is the one page, which keeps it easy to email, store offline, and host.

## Browser support

Any current Chrome, Edge, Firefox or Safari (desktop and mobile). Requires Web Audio API and `localStorage` (all modern browsers).

## Development

Since there is no build system:

- Edit `index.html` directly.
- Validate the embedded script (Node): extract the `<script>` block and run `node --check`.
- Test layout at several window sizes; on desktop the bento grid keeps the page from scrolling (tiles scroll internally), while < 820 px falls back to a stacked page layout.

## License

[MIT](LICENSE)