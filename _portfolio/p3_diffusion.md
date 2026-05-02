---
title: "Generative AI & Interactive Learning for Annotation-efficient 3D Medical Vision"
# excerpt: "Short description of portfolio item number 1<br/><img src='/images/500x300.png'>"
excerpt: "A generative and interactive medical AI project for annotation-efficient 3D segmentation, combining diffusion-based image-mask synthesis, scribble-supervised learning, attention/CRF regularization, and online human-in-the-loop adaptation. The system reduced dependence on dense expert labels while improving segmentation robustness under limited-label and real-world deployment constraints."
collection: portfolio
permalink: /projects/diffusion_med_image/
---

*Research Fellow at Shenzhen University; Technical Director at PathoVision Co. Ltd. — Shenzhen, China, 2020–2023*

### Background

Medical image segmentation is often limited less by model architecture and more by data. Dense 2D/3D annotations are expensive, slow, and require expert clinical knowledge. In real clinical or research workflows, new imaging protocols, small target structures, domain shifts, and privacy constraints make it difficult to collect enough fully annotated training data.

This project developed a set of annotation-efficient AI methods for medical image segmentation: generative data synthesis, weak supervision, interactive segmentation, and online learning. The goal was to reduce expert annotation cost while keeping segmentation models accurate, adaptable, and practical for real deployment environments.

### Situation and Challenge

The main challenge was that standard supervised segmentation assumes a large set of high-quality image-mask pairs, but this assumption often fails in medical AI.

Key difficulties included:

- Expert annotations are expensive, especially for 3D volumes where dense labeling requires slice-by-slice work.
- Weak annotations such as scribbles are easier to collect, but they lack complete shape and boundary information.
- Synthetic medical images need to preserve both anatomical structure and realistic texture; generating images alone is not enough if they are not paired with reliable annotations.
- Online deployment requires models to adapt as new cases arrive, without retraining from scratch or forgetting earlier knowledge.
- Hospital and clinical settings often require data to stay behind the firewall, making centralized retraining and external data transfer difficult.

### What I Built

I worked on three connected directions for annotation-efficient medical vision.

First, I developed a diffusion-based medical image synthesis framework that generates paired medical images and segmentation annotations. Instead of only generating standalone images, the system uses annotation masks as conditional guidance so that the generated image remains aligned with the target segmentation structure. This makes the synthetic data directly useful for downstream segmentation training.

Second, I developed weakly supervised segmentation methods using scribble annotations. The key idea was to train segmentation models from sparse user-provided scribbles while using attention-based similarity learning and CRF-style regularization to recover structure and boundary information on unlabeled pixels.

Third, I developed interactive and continual-learning frameworks for 3D medical image segmentation. These systems allow users to provide sparse annotations over multiple interaction rounds, propagate them into 3D proxy masks, and dynamically update the segmentation model as new volumes arrive. I also explored multi-scale multi-task distillation to improve robustness under incremental learning, where the model must adapt to new data while preserving knowledge from previous cases.

### How It Works

The generative component used a diffusion probabilistic model for annotation-conditioned synthesis. The [MEDSAD framework](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=sofIFCgAAAAJ&citation_for_view=sofIFCgAAAAJ:_FxGoFyzp5QC) synthesizes paired medical images from provided annotations, addressing the scarcity of image-mask pairs in medical segmentation. To improve image realism, it introduces texture style injection (TSI), which brings texture guidance from real training images into the generation process. It also uses feature frequency domain attention (FFDA) to reduce high-frequency noise in synthesized images. The method was evaluated across MR and ultrasound segmentation tasks, including breast tumor, brain tumor, and nerve structure segmentation, and showed that synthetic image-mask pairs can improve downstream segmentation performance.

The weak-supervision component focused on scribble-supervised segmentation. In [AttenScribble](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=sofIFCgAAAAJ&citation_for_view=sofIFCgAAAAJ:roLk4NBRz8UC), I proposed a pluggable spatial self-attention module that can be attached to FCN-style segmentation backbones. The module introduces global spatial interactions while preserving the efficiency of convolutional networks. From the learned attention, the framework constructs an attentive similarity loss, combined with partial segmentation loss and masked CRF regularization, so that the model can learn from sparse scribbles without relying on full pseudo-label propagation. Experiments on ACDC and CHAOS showed that the method outperformed existing weakly supervised approaches and achieved performance close to fully supervised benchmarks.

The [interactive online-learning component](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=sofIFCgAAAAJ&citation_for_view=sofIFCgAAAAJ:W7OEmFMy1HYC) treated annotation and training as a dynamic loop rather than a one-time offline process. For each 3D volume, sparse user inputs are propagated into a 3D proxy mask through image registration, which then serves as weak supervision for model updates. The segmenter, in return, guides the next round of user interaction through a residual map that highlights uncertain or inconsistent regions. To handle streaming data, the framework uses replay, loss weighting, and label smoothing to mitigate catastrophic forgetting and improve online learning robustness.

A related [incremental-learning component](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=sofIFCgAAAAJ&citation_for_view=sofIFCgAAAAJ:2osOgNQ5qMEC) used multi-scale multi-task distillation to mitigate forgetting during sequential 3D segmentation training. The model was trained not only against new supervision, but also against uncertainty-weighted predictions from the previous model, while multi-scale feature representations participated in contrastive learning to preserve discriminative knowledge across updates. This made the framework more robust when data arrived one case at a time and full offline retraining was impractical.

### Impact

Together, these methods reduced the dependency on dense expert annotations from three complementary angles: generating synthetic image-mask pairs, learning from weak scribble annotations, and adapting interactively from sparse user input.

The diffusion-based framework improved downstream segmentation under limited-label settings by augmenting training data with realistic paired image-mask samples. The weak-supervision framework made sparse scribbles more useful by introducing attention-driven visual affinity and boundary-aware regularization. The interactive online-learning system achieved competitive 3D segmentation performance with substantially reduced annotation effort; in evaluation, the framework produced robust results with labeling cost equivalent to at most about 38% of full annotation effort, and the paper reports roughly 62% reduction in total annotation effort while remaining competitive with full-ground-truth online/offline learning.

More broadly, this project shaped my view of generative AI as a practical data engine: not only generating visually plausible samples, but generating usable training data, supervision signals, and human-in-the-loop workflows for domains where labels are scarce, expensive, or privacy constrained.