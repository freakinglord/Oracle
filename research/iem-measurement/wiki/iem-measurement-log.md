<!--
Append-only log. One entry per change, newest at the bottom.
Format:
## [YYYY-MM-DD HH:MM] <ingest|query|lint|new-topic> | <short title>
<1-2 line summary of what changed and which pages were touched>

Get the timestamp with: date +"%Y-%m-%d %H:%M"
-->

## [2026-09-18 13:44] new-topic | IEM Measurement & Graphing Tools
Scaffolded topic to hold research on IEM/headphone frequency-response measurement tooling.

## [2026-09-18 13:44] ingest | mlochbaum/CrinGraph GitHub README
Created cringraph.md from the GitHub README clipping. Covers what CrinGraph is/does, and notes the user's question on overlaying a song's spectrum with an IEM's FR curve (different metric types; legitimate combined use is predicting perceived tonal balance of specific content).

## [2026-09-22 16:40] query | FFT, song vs. track, spectrogram windowing
Created fft-and-spectrograms.md: FFT/STFT basics, song/track distinction (content spectrum vs. fixed device FR curve), de facto windowing convention (2048 samples, Hann, 50-75% overlap), and an ASCII spectrogram visual. Cross-linked from cringraph.md.

## [2026-09-22 16:55] query | Content-aware FR prediction method + data checklist
Created content-aware-fr-prediction.md: sum-in-dB method for combining a track's spectrum with an IEM's FR curve, walked through illustratively for Wet Sand + Kefine Loric (no real data). Documents exact data needed to make it real: Kefine Loric raw FR export, Wet Sand audio file under raw/. Cross-linked from cringraph.md and fft-and-spectrograms.md.
