---
title: "MCMC Guided CNN Training and Segmentation for Pancreas Extraction"
collection: publications
category: manuscripts
permalink: /publication/2021-06-23-mcmc-guided-cnn-pancreas
excerpt: "A probabilistic CNN-based pancreas segmentation method that uses MCMC sampling to guide 3D patch selection during training and segmentation, addressing anatomical variability, small organ size, and fuzzy boundaries in abdominal CT."
date: 2021-06-23
venue: "IEEE Access"
paperurl: "https://doi.org/10.1109/ACCESS.2021.3070391"
citation: '<strong>Tian, M.</strong>, He, J., Yu, X., Cai, C., & Gao, Y. (2021). &quot;MCMC Guided CNN Training and Segmentation for Pancreas Extraction.&quot; <i>IEEE Access</i>, 9, 90539–90554.'
---

This work addresses pancreas segmentation from abdominal CT, a challenging medical image segmentation problem due to the pancreas’s high anatomical variability, small relative volume, and fuzzy organ boundaries.

The method combines registration, Markov Chain Monte Carlo (MCMC) sampling, CNN-based 3D patch segmentation, and Bayesian voting. Registration is first used to reduce variation in patient body shape and organ location. MCMC sampling then guides the selection of informative 3D patches for CNN training while learning a probabilistic distribution of pancreas locations. During inference, another MCMC process guides the segmentation search, and patch-level predictions are fused through Bayesian voting.

The project reflects my early interest in combining probabilistic modeling with deep learning for medical image analysis. Instead of relying only on dense sliding-window segmentation, the framework uses probabilistic sampling to focus computation on likely pancreas regions and improve robustness under large anatomical and imaging variability.