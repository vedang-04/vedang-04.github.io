---
layout: page
title: Age and Gender Detection for a Low-Resolution Video Surveillance Feed
description: Project done for Inter IIT Tech Meet 10.0 conducted by Bosch AI, India
img: assets/img/ts1.png
importance: 3
category: work
related_publications: false
---

The project proposes a gait-based approach to predict age and gender from surveillance video. Rather than relying on directly identifiable facial or physical features, the approach analyzes people's walking movement patterns. The proposed system is designed to work with surveillance footage and aims to provide demographic information while being more robust to variations in physique and walking viewpoint.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts2.png" title="CT scan1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts21.png" title="CT scan2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts3.png" title="our pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our developed 3-stage pipeline
</div>

The proposed pipeline consists of six major stages:

1. **Object Detection:** YOLOv4 is used to detect people in each frame. It is modified for pedestrian detection and chosen for its computational efficiency and suitability for real-time detection.
2. **Multi-Object Tracking:** DeepSORT tracks detected individuals across frames using their deep features along with a Kalman-filter-based prediction and update mechanism.
3. **Super-Resolution:** ESRGAN is applied to cropped, low-quality images of tracked people to generate higher-resolution and more realistic images.
4. **Segmentation:** A U-Net trained on the OCHuman dataset performs semantic segmentation to obtain background-subtracted silhouettes of the detected individuals.
5. **Gait Sequencing:** The segmented silhouettes are aggregated using the **n-MMI (n-Mean Masked Image)** baseline to generate a **Gait Energy Image (GEI)**, which captures the person's walking pattern.
6. **Age and Gender Prediction:** The resulting GEI is passed to separate CNN models for age and gender prediction. The models are trained using the TUM-GAID dataset, with gender treated as a binary classification task and age represented using discrete ages from 10–60 years for regression.

The complete pipeline processes surveillance video to detect and track pedestrians, generate individual cropped-person sequences, and produce demographic predictions with associated timestamps. The system also performs post-processing of the predictions: a dynamic age range is determined using **quartiles**, while gender is determined using the **mode** of the predictions. The report identifies several advantages of the gait-based approach, including **invariance to physique and walking viewpoint**, applicability to situations such as **COVID-type scenarios**, and reduced dependence on directly tangible/identifying features. However, the system can suffer from false classifications, depends on obtaining a sufficiently long gait sequence, requires high-quality segmentation masks, and can lose temporal consistency during processing.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts4.png" title="result scan1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts41.png" title="result scan2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ts5.png" title="result scan1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="caption">
        Intermediate results from our pipeline
</div>

The project demonstrates a complete **gait-based age and gender prediction pipeline** for surveillance video. By combining pedestrian detection, multi-object tracking, super-resolution, silhouette segmentation, gait representation, and CNN-based demographic prediction, the proposed approach provides an alternative to conventional multi-camera re-identification systems. The authors suggest that the system could be improved through more sophisticated gait-sequence encoding techniques. They also propose that the post-processing strategy, designed to imitate aspects of human decision-making, can support more confidence-based probabilistic predictions.

To learn more about this project, please refer to the full project <a href="https://drive.google.com/file/d/10U8sbp7apdmFNClhxeYtIpGwwFW8iTkI/view?usp=drive_link" target="_blank">report</a>  and  <a href="https://drive.google.com/file/d/1QW9TDjgc8pNeC1jJk2Trp33F4jGwr879/view?usp=sharing" target="_blank">video</a>
