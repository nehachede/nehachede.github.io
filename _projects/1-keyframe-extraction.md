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
- Compared three classical key frame extraction techniques: SSIM, entropy-based, and Euclidean distance methods  
- Analyzed trade-offs between compression efficiency and computational complexity  
- Studied shot boundary detection as a foundational step for video segmentation  
- Identified SSIM-based approach as the most balanced in performance and simplicity  

### Data & Method Overview
- Worked with standard video sequences containing multiple shot transitions (cuts, fades, dissolves)  
- Represented videos structurally as frames → shots → scenes  
- Applied shot boundary detection as a preprocessing step before key frame selection  
- Evaluated key frame candidates based on visual similarity, entropy, and edge variation  

### Analytical Approach
The study followed a comparative evaluation framework across three methods:

- Structural Similarity Index (SSIM)
  - Measured perceptual similarity between frames
  - Detected shot transitions using similarity thresholds
  - Selected key frames at high-change boundaries

- Entropy-based method
  - Computed information content using pixel intensity distribution
  - Selected frames with highest information richness
  - Treated entropy as a local rather than global feature

- Euclidean distance method
  - Used edge detection (Canny filter) to extract structural features
  - Measured frame-to-frame pixel variation using distance metrics
  - Identified key frames based on thresholded difference scores  

To evaluate performance:
- Compared methods using Compression Ratio (CR), Processing Time (PT), and Computational Efficiency (CE = CR / PT)
- Analyzed sensitivity of threshold selection on output key frames
- Assessed robustness across different video transition types  

### Key Takeaways & Conclusion
- SSIM-based method consistently outperformed entropy and Euclidean approaches  
- Provided the best balance between compression efficiency and computational cost  
- Entropy and Euclidean methods were more sensitive to parameter tuning and noise  
- Key frame quality strongly depended on accurate shot boundary detection  

### Future Scope
- Extend to deep learning-based temporal models for adaptive key frame selection  
- Improve detection of gradual transitions such as fades and dissolves  
- Enhance robustness for real-world noisy video sequences  
- Scale to long-duration video summarization and real-time processing  

<i>Tech Stack: Python, OpenCV, NumPy, SciPy, Matplotlib</i>