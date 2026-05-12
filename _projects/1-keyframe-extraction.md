---
title: "Automatic Key Frame Extraction "
collection: projects
permalink: /projects/1-keyframe-extraction
excerpt: 'Compared classical key frame extraction techniques for video summarization using SSIM, entropy, and edge-based methods to evaluate compression efficiency and computational performance.'
---

### Introduction

Videos contain large amounts of redundant visual information, making efficient summarization essential for tasks like indexing, retrieval, and compression. Key frame extraction addresses this by selecting representative frames that capture the essence of a video.

This project explores classical approaches to automatic key frame extraction and evaluates their effectiveness in terms of accuracy, compression, and computational efficiency.

### Key Highlights
- Implemented shot boundary detection and automatic key frame extraction pipelines
- Compared three extraction approaches:
  - Structural Similarity Index (SSIM)
  - Entropy difference
  - Edge-based Euclidean distance
- Evaluated methods using:
  - Compression Ratio (CR)
  - Processing Time (PT)
  - Computational Efficiency (CE = CR / PT)
- Analyzed the effect of threshold selection on segmentation quality and extracted frames
- Identified SSIM-based extraction as the most balanced approach in terms of accuracy and computational cost

### Methodology
Videos were segmented into shots by detecting abrupt cuts and gradual transitions between adjacent frames. These segmented shots formed the basis for representative frame extraction.

The study followed a comparative evaluation framework across three methods:

- Structural Similarity Index (SSIM)
	- Measured perceptual similarity using luminance, contrast, and structural information
	- Detected scene transitions from significant drops in similarity scores
	- Produced visually meaningful and stable key frames

- Entropy-based method
  - Computed information content using pixel intensity distribution
  - Selected frames with highest information richness
  - Treated entropy as a local rather than global feature

- Euclidean distance method
  - Used edge detection (Canny filter) to extract structural features
  - Measured frame-to-frame pixel variation using distance metrics
  - Identified key frames based on thresholded difference scores  

### Results
- SSIM-based extraction achieved the best trade-off between summarization quality and computational efficiency
- Entropy and Euclidean methods were more sensitive to parameter tuning and noise  
- Key frame quality strongly depended on accurate shot boundary detection  

### Future Scope
- Adaptive thresholding for dynamic scene transitions
- CNN-based temporal feature extraction for semantic summarization
- Hybrid approaches combining perceptual and deep visual features
- Real-time processing for long-duration video analytics pipelines


<i>Tech Stack: Python, OpenCV, NumPy, SciPy, Matplotlib</i>