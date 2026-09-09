# Deep Learning-Based Stoma Image Classification for Remote Patient Monitoring

> Normal/abnormal classification of patient-captured stoma images with explicit analysis of model attention, shortcut learning, and robustness.

**Period:** Sep. 2025 - Dec. 2025  
**Affiliation:** Machine Learning & Data Mining Laboratory, Ajou University  
**Type:** Collaborative medical-image research  
**Data:** 722 smartphone-captured stoma images from 264 patients  
**Core methods:** ConvNeXt · Grad-CAM · ROI-centered preprocessing · Label Smoothing

---

## Overview

This research developed a deep-learning pipeline for **normal / abnormal classification** of smartphone-captured stoma images for remote patient monitoring.

The project did not stop at predictive performance. It also examined **whether the model was actually attending to the stoma region**. Grad-CAM analysis revealed that some predictions depended on surrounding background rather than the clinically relevant region, indicating **background shortcut learning**.

The final pipeline therefore combined **ConvNeXt**, **Grad-CAM-based failure analysis**, **ROI-centered preprocessing**, and **Label Smoothing** to improve robustness.

## Data & task

- **264 patients**
- **722 smartphone-captured stoma images**
- Binary classification: **normal vs. abnormal**
- Non-standardized patient-captured images with variation in lighting, angle, distance, and background

## Modeling pipeline

1. Train a **ConvNeXt-based** stoma-image classifier.
2. Inspect model attention using **Grad-CAM**.
3. Identify predictions that rely on surrounding background / acquisition context.
4. Apply **ROI-centered preprocessing** to emphasize the clinically relevant stoma region.
5. Apply **Label Smoothing** to improve model robustness.
6. Re-evaluate predictive performance after robustness-oriented changes.

## Main results

| Stage | AUC |
|---|---:|
| Baseline | **0.8919** |
| Final pipeline | **0.9200** |

The final pipeline improved AUC from **0.8919 to 0.9200**.

More importantly, the study showed that a model with strong predictive performance can still depend on **clinically irrelevant shortcut features**.

## Explainability & failure analysis

![Grad-CAM concept](assets/figure-02-gradcam-concept.svg)

Grad-CAM inspection showed that some predictions focused on surrounding gauze or other background context instead of the stoma region. This finding motivated the ROI-centered preprocessing strategy and directly informed the subsequent lesion-localization research.

![Background-bias concept](assets/figure-03-background-bias.svg)

## Research insight

In medical imaging, a high discrimination score alone does not guarantee that the model is using clinically meaningful evidence. This project therefore treated **interpretability and failure analysis as part of model validation**, not as a post-hoc visualization step.

The observed background shortcut problem became the motivation for explicitly localizing the clinically relevant lesion region in the follow-up localization study.

## Historical project-stage note

An earlier project stage used **EfficientNet-B0** under stratified 5-fold evaluation and reported AUC **0.8919 ± 0.0057**. The current portfolio framing uses the later **ConvNeXt-based pipeline** and the final AUC **0.9200** after ROI-centered preprocessing and Label Smoothing.

These stages are kept separate to avoid mixing results from different experimental versions.

## My contribution

The original project materials report a 5:5 contribution split between Junha Won and Seunghyun Park. My recorded contributions include:

- Idea exploration
- Data preprocessing
- Methodology design
- Model experiments
- Grad-CAM / failure analysis
- Visualization and presentation development

## Public outputs

- [`outputs/classification-public-technical-excerpt.pdf`](outputs/classification-public-technical-excerpt.pdf) — public-safe technical excerpt derived from the original project presentation.
- [`outputs/PROJECT_OUTPUTS.md`](outputs/PROJECT_OUTPUTS.md) — source manifest, versioned result notes, and technical provenance.

## Data & privacy

No original patient-captured stoma images or raw clinical data are included in this repository.

---

**Junha Won** · Ajou University  
[Portfolio detail](https://juna0926.github.io/Portfolio/research/classification.html) · [Portfolio](https://juna0926.github.io/Portfolio/) · [GitHub](https://github.com/Juna0926)
