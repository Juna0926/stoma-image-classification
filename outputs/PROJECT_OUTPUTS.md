# Project Outputs

This repository documents the public-safe portion of the stoma-image classification research project.

## Current authoritative framing

The current README and Portfolio detail page use the later robustness-oriented pipeline as the primary project framing:

**ConvNeXt → Grad-CAM failure analysis → ROI-centered preprocessing → Label Smoothing**.

The main result is reported as **AUC 0.8919 → 0.9200**, together with the finding that some predictions relied on surrounding background rather than the clinically relevant stoma region.

## Portfolio-aligned representative figure

- Portfolio source: `Juna0926/Portfolio/assets/media/research-classification.webp`
- The README uses this Portfolio figure as the primary visual summary of Grad-CAM inspection and background-shortcut analysis.

## Public artifacts

- [`classification-public-technical-excerpt.pdf`](classification-public-technical-excerpt.pdf) — concise technical excerpt derived from the original presentation. Clinical images, patient-captured examples, and sensitive source material are excluded.
- `../assets/figure-01-baseline-performance.svg` — historical presentation-stage baseline summary.
- `../assets/figure-02-gradcam-concept.svg` — Grad-CAM interpretability / failure-analysis concept.
- `../assets/figure-03-background-bias.svg` — public-safe reconstruction of the observed background-bias finding.

## Result provenance

Two experimental stages are intentionally kept separate:

1. **Earlier project stage:** EfficientNet-B0 under stratified 5-fold evaluation, AUC **0.8919 ± 0.0057**.
2. **Current Portfolio framing:** ConvNeXt-based pipeline with ROI-centered preprocessing and Label Smoothing, final AUC **0.9200**; the baseline reference used in the Portfolio is **0.8919**.

These values should not be interpreted as results from one identical evaluation protocol. The current README clearly labels the EfficientNet result as a historical project-stage note.

## Research interpretation

The central technical insight is not only the AUC change. Grad-CAM inspection identified **background shortcut learning**, motivating robustness-oriented preprocessing and the later lesion-localization study.

## Public-release policy

The original full presentation is not redistributed because it contains patient-captured clinical imagery. Raw clinical data are not included.
