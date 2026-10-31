# Samples

One folder per drum. Drop the recordings in and list them in `../kit.json`.

## Naming

`<layer>-<take>.wav`, for example:

```
snare/soft-1.wav  snare/soft-2.wav
snare/med-1.wav   snare/med-2.wav
snare/hard-1.wav  snare/hard-2.wav
```

- **Layers** (soft, med, hard) are picked by how hard a step is played, so ghost notes sound like ghost notes.
- **Takes** (1, 2, 3 ...) within a layer rotate on every hit, so repeated hits don't sound identical.

## Preparing files

- Mono or stereo WAV, 44.1 or 48 kHz. M4A or MP3 also decode in browsers, with a little latency padding at the start.
- Trim each file tight to the start of the hit, or the timing feel goes soft.
- Store samples as plain files, not Git LFS: GitHub Pages may not serve LFS files.
- Only commit recordings you made or have a licence to share.

## Status

The app does not play these files yet. Sample playback (velocity layers, takes, the open-hat choke) is the next step.
