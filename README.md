# Deep Learning-Based Stoma Image Classification for Remote Patient Monitoring

> Robust normal/abnormal classification of patient-captured stoma images, with explicit analysis of model attention and background shortcut learning.

**Period:** Sep. 2025 - Dec. 2025  
**Affiliation:** Machine Learning & Data Mining Laboratory, Ajou University  
**Type:** Collaborative medical-image research  
**Data:** 722 smartphone-captured stoma images from 264 patients  
**Core methods:** ConvNeXt · Grad-CAM · ROI-centered preprocessing · Label Smoothing

---

## Overview

This research developed a deep-learning pipeline for **normal / abnormal classification** of smartphone-captured stoma images for remote patient monitoring. Beyond predictive performance, the study examined **where the model was looking** and found that some predictions relied on surrounding background rather than the stoma region itself.

The project therefore focused on both performance and robustness: identifying background shortcut learning with Grad-CAM, then reducing clinically irrelevant background dependence through ROI-centered preprocessing and Label Smoothing.

## Data & task

- **264 patients**
- **722 smartphone-captured stoma images**
- Binary task: **normal vs. abnormal**
- Non-standardized patient-captured images with variation in lighting, angle, distance, and background

## Modeling pipeline

1. Build a deep-learning classification pipeline using **ConvNeXt**.
2. Inspect model attention with **Grad-CAM**.
3. Identify cases in which predictions depend on surrounding background / acquisition context.
4. Apply **ROI-centered preprocessing** to emphasize the clinically relevant stoma region.
5. Apply **Label Smoothing** to improve model robustness.
6. Re-evaluate predictive performance after the robustness-oriented changes.

## Main results

| Stage | AUC |
|---|---:|
| Baseline | **0.8919** |
| Final pipeline | **0.9200** |

The main research insight was not only the AUC improvement, but the observation that a strong classifier can still learn **shortcut features** that are not clinically meaningful.

## Explainability & failure analysis

![Grad-CAM concept](assets/figure-02-gradcam-concept.svg)

Grad-CAM inspection showed that some predictions focused on surrounding gauze or other background context instead of the stoma region. This failure mode motivated the ROI-centered preprocessing strategy and later lesion-localization research.

![Background-bias concept](assets/figure-03-background-bias.svg)

## Earlier project-stage baseline

The original project presentation also documented an **EfficientNet-B0** baseline under stratified 5-fold evaluation. That earlier stage reported AUC **0.8919 ± 0.0057**. The current portfolio framing uses the later **ConvNeXt-based classification pipeline** and reports the final AUC of **0.9200** after ROI-centered preprocessing and Label Smoothing.

Keeping these stages separate avoids mixing results from different versions of the project.

## My contribution

The original project materials report a 5:5 contribution split between Junha Won and Seunghyun Park. My recorded contributions include:

- Idea exploration
- Data preprocessing
- Methodology design
- Model experiments
- Grad-CAM / failure analysis
- Visualization and presentation development

## Public outputs

- [`outputs/classification-public-technical-excerpt.pdf`](outputs/classification-public-technical-excerpt.pdf) - public-safe technical excerpt derived from the original project presentation.
- [`outputs/PROJECT_OUTPUTS.md`](outputs/PROJECT_OUTPUTS.md) - source manifest, versioned result notes, and technical provenance.
- The full presentation is not publicly redistributed because it contains clinical images.

## Data & privacy

No original patient-captured stoma images or raw clinical data are included in this repository.

---

**Junha Won** · Ajou University  
[Portfolio detail](https://juna0926.github.io/Portfolio/research/classification.html) · [Portfolio](https://juna0926.github.io/Portfolio/) · [GitHub](https://github.com/Juna0926)
