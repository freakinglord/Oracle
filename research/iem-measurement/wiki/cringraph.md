---
title: CrinGraph
tags: [iem, headphones, frequency-response, audio-measurement, tooling]
source: https://github.com/mlochbaum/CrinGraph
source_type: url
created: 2026-09-18
updated: 2026-09-22 16:40
---

# CrinGraph

## Overview
CrinGraph is an open-source, in-browser tool for viewing and comparing in-ear monitor (IEM) / headphone frequency response (FR) measurements. Built by mlochbaum for reviewer Crinacle's site; freely reusable, with several other public instances (Banbeucmas, HypetheSonics, squig.link and its linked directory).

## Key Points

### What it plots
- Frequency response (FR): loudness (dB SPL) vs. pitch (Hz), log-frequency axis — the standard headphone measurement.
- It's a **device transfer function**: how a given IEM colors a flat input across the spectrum. Content-independent — it doesn't know or care what audio is playing.
- Data is pre-measured (sine sweep or similar) and loaded as static curve files; CrinGraph itself has no audio decode/playback/FFT pipeline.

### Features
- Graph window: log Hz/dB axes, persistent algorithmic curve coloring for contrast, hover/click to highlight.
- Toolbar: zoom bass/mid/treble, normalize (target loudness or frequency), configurable smoothing, inspect mode (numeric values on hover), in-graph labeling, PNG screenshot export.
- Selectors: headphones grouped by brand, independent target-curve selector, search across both.
- Manager: per-curve color/name, variant measurement dropdown, L/R channel or averaged view, channel-imbalance flag, offset adjustment, BASELINE (normalize all curves flat against a chosen one), hide/pin, per-curve recolor.
- Config docs at `Configuring.md` in the repo for anyone standing up their own instance.

### Song spectrum vs. IEM FR curve — do they combine?
Prompted by a question about adding a song's frequency response and analyzing an IEM's profile against it. Two distinct metric types:
- **IEM FR curve** (what CrinGraph plots) = transfer function of the device. Same curve regardless of what's playing through it.
- **Song spectrum** = spectral energy distribution of one specific audio track (via FFT/spectrogram) — a property of the content, not the device.
- They're not directly comparable as-is, but there's a legitimate combined use: adding (in dB) a track's average spectrum to an IEM's deviation-from-target curve estimates how that IEM will tonally color that specific track — a real technique used for mastering/translation checks.
- That's a materially different feature from CrinGraph's data model, though: it needs an audio decode + FFT/spectrogram step (feasible client-side via Web Audio API) that the tool doesn't have. Would be a separate prototype/fork, not a patch to the curve viewer.

## Related
- [[fft-and-spectrograms]] — the FFT/STFT mechanics behind "song spectrum" mentioned above, plus what a spectrogram actually looks like.
- [[content-aware-fr-prediction]] — the actual sum-in-dB method for combining a track's spectrum with an IEM's FR curve, plus the data checklist to run it for real.

## Open questions / gaps
- No sample of the underlying FR measurement file format has been ingested yet (see `Documentation.md` in the repo) — would help if evaluating CrinGraph for a personal graphing setup.
- The song-spectrum-overlay idea above is unimplemented/untested — flagging as a possible future build, not an existing feature of CrinGraph.
