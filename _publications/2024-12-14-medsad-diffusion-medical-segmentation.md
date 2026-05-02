---
title: "Synthesizing Images With Annotations for Medical Image Segmentation Using Diffusion Probabilistic Model"
collection: publications
category: manuscripts
permalink: /publication/2024-12-14-medsad-diffusion-medical-segmentation
excerpt: "A diffusion-based medical image synthesis framework that generates annotation-aligned image-mask pairs, using texture style injection and frequency-domain attention to improve realism and downstream segmentation under limited-label settings."
date: 2024-12-14
venue: "International Journal of Imaging Systems and Technology"
paperurl: "https://doi.org/10.1002/ima.70007"
citation: 'Huang, Z., Yang, Q., <strong>Tian, M.</strong>, & Gao, Y. (2024). &quot;Synthesizing Images With Annotations for Medical Image Segmentation Using Diffusion Probabilistic Model.&quot; <i>International Journal of Imaging Systems and Technology</i>, 35(1), e70007.'
---

This work studies how diffusion models can be used not only to synthesize realistic medical images, but also to generate training data that is directly useful for segmentation. In medical image analysis, labeled image-mask pairs are often scarce because dense annotation requires expert effort. Generating standalone images is therefore insufficient; synthetic samples must remain aligned with valid segmentation annotations.

The proposed MEDSAD framework uses segmentation masks as conditional guidance to synthesize corresponding medical images, producing paired image-mask samples for downstream segmentation training. To improve the realism and controllability of synthesized medical images, the method introduces texture style injection (TSI), which incorporates texture information from real training images. It also uses feature frequency domain attention (FFDA) to reduce high-frequency noise during generation.

The method was evaluated across multiple medical segmentation tasks and modalities, including MR and ultrasound images for breast tumor, brain tumor, and nerve structure segmentation. Experiments showed that the generated image-mask pairs can augment training data and improve downstream segmentation performance under limited-label settings.

This paper reflects my broader interest in generative AI as a practical data engine: using diffusion models to create structured, annotation-aligned training data for domains where labels are scarce, expensive, or difficult to share.