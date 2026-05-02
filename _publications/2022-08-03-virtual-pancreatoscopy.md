---
title: "Open-source Algorithm and Software for Computed Tomography-based Virtual Pancreatoscopy and Other Applications"
collection: publications
category: manuscripts
permalink: /publication/2022-08-03-virtual-pancreatoscopy
excerpt: "An open-source 3D Slicer-based virtual pancreatoscopy platform that combines pancreatic duct segmentation, optimal path planning, and super-resolution to enable CT-based fly-through visualization and quantitative duct analysis."
date: 2022-08-03
venue: "Visual Computing for Industry, Biomedicine, and Art"
paperurl: "https://doi.org/10.1186/s42492-022-00116-1"
citation: 'Huang, H., Yu, X., <strong>Tian, M.</strong>, He, W., Li, S. X., Liang, Z., & Gao, Y. (2022). &quot;Open-source Algorithm and Software for Computed Tomography-based Virtual Pancreatoscopy and Other Applications.&quot; <i>Visual Computing for Industry, Biomedicine, and Art</i>, 5, Article 20.'
---

This work presents an open-source software platform for CT-based virtual pancreatoscopy. Traditional pancreatoscopy can support diagnosis and treatment of pancreatic diseases, but it is highly invasive and carries greater procedural risk than many other endoscopic examinations. Virtual pancreatoscopy provides a safer computational alternative, but it is technically challenging because the pancreatic duct is small and difficult to reconstruct from standard CT resolution.

The proposed system combines pancreatic duct segmentation, optimal path planning, and super-resolution techniques within a 3D Slicer-based software platform. The segmentation component extracts the pancreatic duct from abdominal CT, while the visualization pipeline reconstructs fly-through views inside and outside the duct. The system also supports quantitative analysis such as duct wall thickness and topology, offering information beyond visual inspection alone.

The study reported an average Dice coefficient of 0.85 ± 0.04 for pancreatic duct segmentation and released the software as an open-source package for validation, testing, and future clinical research.

This paper reflects my broader interest in practical medical AI systems: combining segmentation, visualization, quantitative analysis, and open-source software to make imaging algorithms more accessible for clinical and biomedical research.