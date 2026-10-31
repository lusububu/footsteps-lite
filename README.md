# Footsteps Lite

A 16-step drum machine for the phone: the Footsteps 808 voices, a sequencer with eight patterns, drummer-feel knobs and three effects. One HTML file, no build step.

## Run it

- **Locally:** serve the folder with any static server, for example `python3 -m http.server`, then open `http://localhost:8000`. Opening `index.html` straight from disk plays the synth voices, but samples won't load that way.
- **GitHub Pages:** Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`.

## Layout

```
index.html     the app
kit.json       which sample plays for each row and velocity
samples/       the acoustic kit: 40 WAV files (see samples/README.md)
.nojekyll      tells GitHub Pages to serve the files as they are
```

## What it does

- **Sequencer:** 10 rows, 16 steps. Tap a step to cycle on, soft, off; drag to paint; tap a row name to mute.
- **Patterns:** 8 slots. While playing, a tapped slot starts on the next bar. Chain plays every slot that has steps, in order.
- **Drummer feel:** Swing (16ths or 8ths), Looseness, Kick ghosts, Snare ghosts, Hat variation, Touch, Hat fills. Timing drifts with long-range (1/f) correlation, after Hennig et al. (2011).
- **Effects:** Chorus → Tape echo → Reverb (Plate, Hall, Room) → Level → limiter.

Settings and patterns are saved in the browser on each device.

## Samples

The app reads `kit.json` and loads the acoustic kit from `samples/` (short drums first, cymbals last). Each hit picks a velocity layer, rotates through that layer's takes and follows the velocity in level; a closed hat chokes a ringing open hat. The Acoustic / 808 switch under the grid swaps kits while playing. A row without samples (Rim, Clap, Cowbell), or one still loading, plays its 808 voice.

Samples load only when the page is served over http, so they work on GitHub Pages and a local server, not from a file opened on disk.

## Source

The voice engine, the resonator and cymbal worklets, the reverb impulse responses, the echo and chorus chain and the drummer's body come from Footsteps Mobile.
