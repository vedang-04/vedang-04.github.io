---
layout: page
title: Automatic Discovery and Mapping of Streetlights from Street View Videos
description: Project done with iHub-Data, IIIT Hyderabad, India
img: assets/img/st1.png
importance: 2
category: work
related_publications: false
---

Streetlights are essential for road safety, urban planning, and energy-efficient infrastructure management. However, manually discovering and mapping streetlights across large geographical areas is time-consuming and resource-intensive. This project, GeoLighting, proposes an automated system for discovering and geographically mapping streetlights from GPS-tagged street-view videos, enabling the creation of large-scale streetlight inventories without requiring specialized infrastructure.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/st2.png" title="CT scan1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/st21.png" title="CT scan2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/st3.png" title="our pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our developed 3-stage pipeline
</div>

We developed a three-stage pipeline for automatic streetlight discovery and geo-localization: 

Object Detection: Streetlights are detected from street-view video frames using state-of-the-art object detectors, with YOLOv8n selected as the best-performing model.

Feature Extraction and Matching: Feature points are extracted from detected streetlights using ORB and matched across consecutive frames to identify and eliminate duplicate instances.

Geo-Tagging: GPS coordinates corresponding to frames containing the same streetlight are aggregated to assign a final geographical location.

The system was evaluated on a custom dataset containing 10,000 street-view frames and 2,500 annotated streetlights, collected across Hyderabad, Warangal, and Vikarabad to represent urban, semi-urban, and rural environments.

YOLOv8n achieved the best detection performance with a mAP@0.5 of 98.7%, outperforming the next-best baseline by approximately 5%. The complete pipeline achieved average localization errors ranging from 1.35 m in rural regions to 2.70 m in urban regions. The system was successfully evaluated across diverse environments with varying streetlight structures, occlusions, backgrounds, and levels of urbanization. The complete detection, feature extraction, matching, and GPS assignment pipeline operates in under one second per streetlight instance, demonstrating its potential for real-time deployment.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/st4.png" title="result scan1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-2 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/st41.png" title="result scan2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="caption">
        Results from our pipeline
</div>

GeoLighting demonstrates that streetlights can be automatically discovered and geographically mapped using only GPS-augmented street-view imagery. By combining object detection, feature matching, and GPS-based localization, the proposed pipeline provides an efficient and scalable alternative to manual streetlight mapping. The system can support applications in urban planning, infrastructure monitoring, and energy-efficient streetlight placement, with future work focused on scaling the system into a dashboard-based service for civic authorities and planning agencies.

To learn more about this project, please refer to the full project <a href="https://drive.google.com/file/d/1VEiGzWKokakuyZvj30wzdwH3Tov3Y9ss/view?usp=drive_link" target="_blank">report</a> and <a href="https://drive.google.com/file/d/1y0L751IP0e_t8kepxyQKz2fJvcQym2ti/view?usp=drive_link" target="_blank">video</a>
