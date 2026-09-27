---
title: IEM Measurement & Graphing Tools
category: research
created: 2026-09-18
updated: 2026-09-22 16:55
---

# IEM Measurement & Graphing Tools

Tooling and technique for reading, comparing, and visualizing in-ear monitor (IEM) / headphone frequency response measurements.

## Pages

- [CrinGraph](cringraph.md) — open-source in-browser FR graph comparison tool built for Crinacle's IEM measurements; also covers the song-spectrum-vs-FR-curve question (device transfer function vs. content spectrum, and where combining them is legitimate).
- [FFT and Spectrograms](fft-and-spectrograms.md) — FFT/STFT basics, common windowing convention (2048 samples, Hann, 50-75% overlap), and a rough visual of what a song's spectrogram looks like.
- [Content-Aware FR Prediction](content-aware-fr-prediction.md) — method for summing a track's spectrum with an IEM's FR curve to predict tonal coloration on that specific song; data checklist (IEM FR file + raw audio) needed to make the Wet Sand + Kefine Loric example real.

## Log

See [iem-measurement-log.md](iem-measurement-log.md) for the full history of ingests, queries, and lints on this topic.
