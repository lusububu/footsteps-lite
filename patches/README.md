# Patches

One JSON file per patch. A patch holds a tempo, the drummer-feel and effect settings, and up to eight patterns.

`footsteps-default.json` is the format reference: it holds exactly what Footsteps Lite opens with.

## Pattern rows

Each pattern is a set of 16-character rows, one character per sixteenth note:

| Character | Meaning |
|---|---|
| `x` | hit |
| `o` | soft hit |
| `.` | rest |

| Row | Drum |
|---|---|
| `k` | Kick |
| `s` | Snare |
| `rs` | Rim |
| `cp` | Clap |
| `h` | Hat (closed) |
| `o` | Open hat |
| `lt` | Lo tom |
| `ht` | Hi tom |
| `cb` | Cowbell |
| `cy` | Cymbal |

Rows that are left out are empty. A step can't hold both `h` and `o`; the open hat wins.

## Status

The app does not read this folder yet. Loading patches from here (and a patch picker) is the next step.
