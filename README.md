# REA — REAPER Web

Isaac's own REAPER-inspired web DAW. Use it anywhere, projects save to local storage.

**Live (after Pages is enabled):** https://isaacred718.github.io/rea-reaper-web/
**Short route idea:** /rea

## What it is

A basic practice / production edition in the spirit of REAPER, not Cockos REAPER itself.
Built as a single static `index.html` so it runs on GitHub Pages, phone, laptop, and Quest browser with no server.

## Features

- Transport: play, stop, rewind, record-arm, loop, metronome, BPM and time signature
- Multitrack Arrange: tracks, clips, add/move/select, colour-coded lanes, ruler in bars
- Mixer: channel strips with volume faders, mute/solo
- Piano Roll: 16-step melody writer with Web Audio playback, scale selector
- Drum Pads: 8 Web Audio pads, no samples needed
- Stem Separation workflow (web version of IDW Stem Separator v1.3):
  - Basic 4-Stem (Vocals, Drums, Bass, Other) with Fast / Standard / Ensemble HQ selector
  - Scan for Instruments (adds Guitar, Piano, with dB and % energy)
  - Drums Only (Kick, Snare, Hi-Hat, Toms, Cymbals)
  - Note: browser version creates the stem track structure for mixing/arranging anywhere. Real Demucs separation still runs in desktop REAPER on the Mac, this web panel mirrors that workflow honestly.
- Scaler: Analyse chords, key, tempo and time signature, Add Chord Markers, Create Chord Track, Set Project Tempo with the timebase-safe flow from desktop v1.2
- Projects in local storage:
  - Autosave to `rea.autosave`
  - Named projects in `rea.projects.v1`
  - Export / Import as `.rea.json` to move projects between devices
  - Import audio files (plays in session, name/settings saved, audio stays on your device)

## Deploy on GitHub Pages

1. Create repo `Isaacred718/rea-reaper-web` (public)
2. Push this folder (`index.html`, `README.md`) to `main`
3. Repo Settings, Pages, Deploy from a branch, `main`, `/ (root)`, Save
4. Wait for Pages build, open https://isaacred718.github.io/rea-reaper-web/

No build step, no dependencies, no server.

## Local use

Open `index.html` in any browser, or run:

```bash
python3 -m http.server 8080
```

then open http://localhost:8080

## Honest limits

- Not real REAPER, no VST, no ReaScript, no Demucs in the browser (that model is ~2 GB and runs on the Mac)
- Audio file imports are session playback only, project files save structure, settings, MIDI notes, markers and track data in local storage
- Shareable projects: use Export .rea.json

Built for Isaac Walton, 2026-11-20.
