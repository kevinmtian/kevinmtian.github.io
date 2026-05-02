---
title: "A Dynamic Interactive Learning Framework for Automated 3D Medical Image Segmentation"
collection: publications
category: manuscripts
permalink: /publication/2023-12-11-dynamic-interactive-learning-3d-segmentation
excerpt: "An interactive online-learning framework for 3D medical image segmentation that combines sparse user input, proxy-mask propagation, weak supervision, replay, and label smoothing to reduce annotation effort while maintaining robust segmentation performance."
date: 2023-12-11
venue: "arXiv / CoRR"
paperurl: "https://arxiv.org/abs/2312.06072"
citation: '<strong>Tian, M.</strong>, Chen, X., & Gao, Y. (2023). &quot;A Dynamic Interactive Learning Framework for Automated 3D Medical Image Segmentation.&quot; <i>arXiv preprint arXiv:2312.06072</i>.'
---

This work studies how to make 3D medical image segmentation systems more practical under real deployment constraints, where dense expert annotations are expensive, new data arrive sequentially, and model iteration can be slow.

The proposed framework integrates interactive segmentation, weak supervision, and online continual learning into a unified dynamic training loop. In each interaction round, sparse user inputs are propagated into a 3D proxy mask using image registration, which serves as weak supervision for updating the segmentation model. The model then guides the next round of user intervention through residual maps, helping users focus annotation effort on informative or uncertain regions.

To support streaming data and reduce catastrophic forgetting, the framework introduces replay, loss weighting, and label smoothing strategies. Evaluation on 3D segmentation tasks, including NCI-ISBI2013 and BraTS2015, showed that the framework can achieve online learning performance comparable to offline training while reducing total annotation effort by about 62%.

This paper reflects my broader interest in human-in-the-loop and annotation-efficient medical AI systems: models should not only learn from static fully labeled datasets, but also adapt dynamically from sparse expert feedback in privacy-sensitive clinical environments.