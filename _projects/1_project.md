---
layout: page
title: Brain Ventricle Segmentation With Intraventricular Hemorrhage
description: Project done at the Medical and Environmental Computing Lab, TU Darmstadt, Germany
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

Brain ventricle segmentation is clinically important for monitoring changes in ventricular shape and volume associated with several neurological conditions. However, segmentation becomes particularly challenging in cases of intraventricular hemorrhage (IVH), where blood enters the ventricles and obscures their boundaries. This project investigates this under-explored problem and proposes a robust segmentation pipeline built on the nnU-Net framework to mitigate the effect of blood interference during ventricle segmentation.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

We propose a three-stage end-to-end pipeline consisting of robust nnU-Net preprocessing followed by two successive U-Nets. The first U-Net performs multi-class segmentation of the background, ventricles, and blood. Its output logits are then combined with the original CT data and passed to a second U-Net, which refines the ventricle segmentation while reducing the risk of incorrectly segmenting blood outside the ventricles as ventricular tissue. The approach was evaluated using 5-fold cross-validation on 40 annotated 3D CT scans, including 22 cases with blood inside the ventricles. Additional experiments investigated symmetry-aware training using flipped volumes and different loss-weighting strategies. The proposed pipeline achieved performance comparable to the strong nnU-Net baseline, with the best pipeline variant achieving a Dice Similarity Coefficient of 82.8 ± 2.2% and an IoU of 71.0 ± 3.2%. The refinement stage improved the intermediate segmentation by approximately 7.95%. Experiments showed that gradient detachment between the two stages was important for stable training. However, exploiting anatomical symmetry through flipped volumes did not improve performance and slightly degraded the results. Overall, the experiments highlighted the robustness of nnU-Net, with the proposed pipeline providing effective mask refinement but no substantial improvement over the baseline.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

This work explores the challenging problem of cerebral ventricle segmentation in the presence of intra-ventricular hemorrhage. A novel three-stage pipeline using two U-Nets within the nnU-Net framework was developed to refine ventricle segmentation and mitigate blood interference. While the proposed method performed consistently and demonstrated effective refinement between stages, the experiments also revealed that the nnU-Net baseline itself is highly robust and difficult to outperform. Future work focuses on developing an extended multi-stage pipeline and improved training strategies for further refinement of ventricle and hemorrhage segmentation. 

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

To learn more about this project, please refer to the full project [report](https://drive.google.com/file/d/1Uo2eT7w-QgDkAMQ1JmpRPm9gKmgIjsR2/view?usp=drive_link)
{% endraw %}
