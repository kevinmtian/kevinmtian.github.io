---
title: "AttenScribble: Attention-enhanced Scribble Supervision for Medical Image Segmentation"
collection: publications
category: manuscripts
permalink: /publication/2025-05-22-attenscribble
excerpt: "A weakly supervised medical image segmentation framework that learns from sparse scribble annotations using pluggable spatial self-attention, attentive similarity regularization, partial segmentation loss, and masked CRF regularization."
date: 2025-05-22
venue: "Journal of Visual Communication and Image Representation"
paperurl: "https://doi.org/10.1016/j.jvcir.2025.104476"
citation: '<strong>Tian, M.</strong>, Yang, Q., & Gao, Y. (2025). &quot;AttenScribble: Attention-enhanced Scribble Supervision for Medical Image Segmentation.&quot; <i>Journal of Visual Communication and Image Representation</i>, 110, 104476.'
---

This work addresses weakly supervised medical image segmentation from sparse scribble annotations. Scribbles are cheaper and more flexible than dense masks, but they provide limited shape and boundary information, making it difficult for segmentation models to generalize to unlabeled pixels.

The proposed AttenScribble framework introduces a pluggable spatial self-attention module that can be attached to internal feature layers of fully convolutional segmentation backbones. The attention module captures global spatial interactions while preserving the efficiency of convolutional networks. From the learned attention maps, the method constructs an attentive similarity loss that encourages consistency between model predictions and visual feature affinity.

The model is trained end-to-end with three objectives: partial segmentation loss on labeled scribble pixels, masked CRF regularization for boundary-aware consistency, and attentive similarity loss for global structure propagation. Experiments on public datasets including ACDC and CHAOS showed that the method outperformed existing weakly supervised approaches and achieved performance close to fully supervised benchmarks.

This paper reflects my broader interest in annotation-efficient medical AI: using attention, weak supervision, and structured regularization to reduce dense expert labeling requirements while maintaining reliable segmentation performance.