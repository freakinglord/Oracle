---
title: Content-Aware FR Prediction (Track Spectrum + IEM FR)
tags: [fft, spectrogram, frequency-response, iem, method]
source: query
source_type: query
created: 2026-09-22
updated: 2026-09-22 16:40
---

# Content-Aware FR Prediction (Track Spectrum + IEM FR)

## Overview
Method for predicting how a specific IEM will tonally color a specific song,
by summing (in dB) that track's averaged spectrum with the IEM's
deviation-from-target FR curve. Walked through illustratively for "Wet Sand"
(RHCP) outro + Kefine Loric — **no real data yet**, shapes were guessed from
genre/tuning-family conventions only. This page is the data checklist to
make it real.

## Key Points
- The math is trivial (per-frequency-bin addition of two dB curves); the
  blocker is entirely data acquisition, not technique.
- Two independent inputs needed, from two independent sources — they don't
  interact until the final sum step.

### Data needed
1. **IEM FR measurement file for Kefine Loric**
   - A raw measurement export (not a screenshot) — CrinGraph/squig.link
     instances publish these as `.txt` or `.csv` (freq, dB pairs, usually
     ~200-400 points log-spaced 20Hz-20kHz).
   - Source: search squig.link's linked directory or Crinacle's own site for
     "Kefine Loric"; if found, save the raw export under `raw/` — do not
     just eyeball a plotted image.
2. **Wet Sand audio, last ~60s**
   - Actual audio file (any lossless/high-bitrate format Web Audio API or a
     Python audio lib can decode — wav/flac/mp3 fine).
   - Needs to be a file I can read (local path under `raw/`), not just "the
     song exists on streaming" — streaming platforms don't expose raw PCM.
3. *(Optional, sharpens the result)* **A target curve** for the Loric's FR
   file to normalize against (e.g. Harman IE target) — most FR file
   directories bundle one; without it, use the Loric's raw curve as-is and
   skip the "deviation from target" step, just diff against a flat line.

### Once both exist
- Decode Wet Sand's last 60s → STFT (2048-sample window, Hann, 50-75%
  overlap, per [[fft-and-spectrograms]]) → average the columns into one
  spectrum.
- Parse the Loric FR file directly (no FFT needed, it's already frequency
  data).
- Resample one onto the other's frequency bins (interpolate — they won't
  share the same Hz grid) and add in dB.
- This step needs actual code (e.g. a small Python script — numpy/scipy for
  the FFT, no new heavy deps) — not something to run inside this chat
  without the files.

## Related
- [[fft-and-spectrograms]] — the FFT/STFT mechanics this method uses on the
  track side.
- [[cringraph]] — where the FR-curve-vs-song-spectrum distinction originated;
  CrinGraph itself doesn't do this combination, it's device-curve-only.

## Open questions / gaps
- Entirely unimplemented — this page is a data checklist + method sketch,
  not a working result. Revisit once the Loric FR file and Wet Sand audio
  are in `raw/`.
