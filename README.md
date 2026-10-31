# Footsteps Lite

A 16-step drum machine for the phone: the Footsteps 808 voices, a sequencer with eight patterns, drummer-feel knobs and three effects. One HTML file, no build step.

## Run it

- **Locally:** serve the folder with any static server, for example `python3 -m http.server`, then open `http://localhost:8000`. Opening `index.html` straight from disk plays the synth voices, but samples and patches won't load that way.
- **GitHub Pages:** Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`.

## Layout

```
index.html     the app
kit.json       which sample file plays for which drum, layer and take
samples/       one folder per drum (see samples/README.md)
patches/       saved settings and patterns (see patches/README.md)
.nojekyll      tells GitHub Pages to serve the files as they are
```

## What it does

- **Sequencer:** 10 rows, 16 steps. Tap a step to cycle on, soft, off; drag to paint; tap a row name to mute.
- **Patterns:** 8 slots. While playing, a tapped slot starts on the next bar. Chain plays every slot that has steps, in order.
- **Drummer feel:** Swing (16ths or 8ths), Looseness, Kick ghosts, Snare ghosts, Hat variation, Touch, Hat fills. Timing drifts with long-range (1/f) correlation, after Hennig et al. (2011).
- **Effects:** Chorus → Tape echo → Reverb (Plate, Hall, Room) → Level → limiter.

Settings and patterns are saved in the browser on each device.

## Still to build

1. Play the samples listed in `kit.json`, falling back to the 808 voice for any drum without files.
2. Load patches from `patches/`, with a picker in the app.

## Source

The voice engine, the resonator and cymbal worklets, the reverb impulse responses, the echo and chorus chain and the drummer's body come from Footsteps Mobile.
