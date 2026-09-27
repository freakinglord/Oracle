---
title: FFT and Spectrograms
tags: [fft, spectrogram, audio-measurement, dsp]
source: query
source_type: query
created: 2026-09-22
updated: 2026-09-22 16:40
---

# FFT and Spectrograms

## Overview
FFT (Fast Fourier Transform) converts a chunk of audio (amplitude over time)
into a spectrum (energy over frequency). A spectrogram is many FFTs run over
successive short windows of a track, stacked to show frequency content
changing over time — the tool that makes "song vs. IEM FR" analysis possible
([[cringraph]]).

## Key Points

- **FFT** = one waveform window in → one spectrum out (energy per Hz, for
  just that window). Static, not time-aware by itself.
- **Spectrogram (STFT — Short-Time FFT)** = FFT repeated over overlapping
  windows, one column per window → a 2D image: time (x), frequency (y),
  color/intensity (loudness at that point).
- **Averaged spectrum** = one FFT (or spectrogram columns averaged together)
  over the *whole* track → single static curve, no time axis. This is the
  one used for the IEM-coloring trick in [[cringraph]].

### De facto "audiophile standard" window
There's no official spec, but common tooling converges on:
- **FFT size: 2048 samples** (at 44.1kHz ≈ 46ms per window) — default in
  Audacity, Spek (the go-to tool audiophiles use to visually check for fake/
  transcoded lossy files), and most DAW spectrum analyzers. 1024 and 4096
  also common depending on whether time or frequency resolution matters more.
- **Window function: Hann** (tapers each chunk's edges to zero before FFT,
  avoids spectral smearing) — the default in nearly every tool above.
- **Overlap: 50–75%** between consecutive windows, so the image is smooth
  rather than blocky as it slides across the track.
- **Time/frequency tradeoff**: bigger FFT window = finer frequency detail
  but blurs fast transients in time; smaller window = sharp in time, coarser
  in frequency. 2048 is the common middle ground for full songs.

## Details

### Rough visual of what a song's spectrogram looks like
Axes: time left→right, frequency (log, bass at bottom to treble at top) up.
Brightness/color = loudness at that time+frequency.

```
20kHz ┤ · · · · · · · · · · · · · · · · · · · · · · · ·   (cymbals/air, sparse)
      │ · · ·▓· · · · · ·▓· · · · · · · ·▓· · · · · ·▓·   (hi-hats: short bright ticks)
 5kHz ┤ ░░░▓░░░░░░░▓░░░░░░░▓░░░░░░░▓░░░░░░░▓░░░░░░░▓░░░   (vocal sibilance, snare crack)
      │ ▓▓▓███▓▓▓▓███▓▓▓▓▓███▓▓▓▓▓███▓▓▓▓▓███▓▓▓▓▓███▓   (vocal + guitar body, dense)
 500Hz┤ ████████████████████████████████████████████████   (bassline, near-continuous)
      │ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░ █▓░   (kick drum: regular pulses)
 20Hz ┤ ▓·· ▓·· ▓·· ▓·· ▓·· ▓·· ▓·· ▓·· ▓·· ▓·· ▓·· ▓··   (sub bass, only on kick hits)
      └──────────────────────────────────────────────────
        0s        intro         verse         chorus →
```

Reading it: continuous horizontal bands = sustained tones (bassline, drone,
held vocal note); vertical streaks = transients (drum hits, plucks); a track
that's dense across all rows in the chorus and sparse in the intro is
literally what "the arrangement builds" looks like as pixels. A lossy/
transcoded file shows as a hard horizontal cutoff (a "brickwall") near
16–19kHz where the encoder threw away content — the classic audiophile use
of Spek is spotting that line.

## Related
- [[cringraph]] — where this came from: distinguishing a track's spectrum
  (this page) from an IEM's fixed FR curve, and the legitimate way to
  combine them.

## Open questions / gaps
- No public formal standard exists (unlike IEM FR measurement conventions);
  the "2048 + Hann + 50-75% overlap" above is convention-by-popular-tooling,
  not a spec. Worth citing a specific tool's docs (Spek, Sonic Visualiser) if
  this needs a harder citation later.
