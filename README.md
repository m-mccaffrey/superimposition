# Superimposition

A single-file web app that takes the guesswork out of **harmonic superimposition** —
improvising with scales over chords to imply different harmonic ideas.

**Live app:** https://m-mccaffrey.github.io/superimposition/

Pick a chord root and quality, and every scale in the dataset — all modes of the
major and melodic minor scales, harmonic minor/major, symmetric scales (whole tone,
diminished, augmented), pentatonics, blues, and bebop scales, at all twelve roots —
is ranked from most *inside* to most *outside* against that chord.

## How it works

- Each note of a candidate scale is classified relative to the chord: **chord tone**,
  **available tension**, **color tension** (e.g. ♯11 on a major chord, altered notes on
  a dominant), **avoid note**, or **clash**.
- The inside score blends the average consonance of the scale's notes with how many
  of the chord's defining tones the scale contains.
- Scale/root combinations with identical pitch content are merged into one row
  (over Cmaj7, C Ionian ≡ D Dorian ≡ G Mixolydian), with equivalent names listed.
- A piano keyboard visualizes the chord against the selected scale, and each scale
  can be auditioned over a synthesized chord pad (Web Audio, no samples).

## Development

Everything lives in `index.html` — no build step, no dependencies. Open it in a
browser to run locally.

## Deployment

The site is served by GitHub Pages from the `gh-pages` branch. To publish changes,
push the updated files to `gh-pages`:

```sh
git push origin <your-branch>:gh-pages
```
