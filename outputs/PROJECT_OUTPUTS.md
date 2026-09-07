# Project Outputs

This repository documents the public-safe portion of the original stoma-image classification research project.

## Public artifacts

- [`classification-public-technical-excerpt.pdf`](classification-public-technical-excerpt.pdf) - concise technical excerpt derived from the original presentation. Clinical images, patient-captured examples, and sensitive source material are excluded.
- `../assets/figure-01-baseline-performance.svg` - presentation-stage baseline performance summary.
- `../assets/figure-02-gradcam-concept.svg` - Grad-CAM interpretability concept used in the project.
- `../assets/figure-03-background-bias.svg` - public-safe reconstruction of the background-bias finding.

## Result provenance

- EfficientNet-B0 baseline AUC: **0.8919 ± 0.0057** from the original project presentation.
- Portfolio/CV optimized AUC: **0.92** after subsequent ROI-centered preprocessing and Label Smoothing.
- These two results correspond to different project stages and are intentionally kept separate.

## Public-release policy

The original full presentation is not redistributed because it contains patient-captured clinical imagery. Raw clinical data are not included.
