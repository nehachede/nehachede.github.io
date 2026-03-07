---
title: "CEnTR*IMPACT Component & Weightings Analysis: Bayesian Updating for Accurate Community Engaged Research Reporting"
collection: research
permalink: /research/1-bayesian-fads
excerpt: "Built an interactive analytics framework combining R, Python, and Streamlit to measure and visualize community-engaged research impact using network modeling, Bayesian alignment metrics, and custom visualizations such as solar correlation and spiral plots."
---

### Introduction

I had the opportunity to work with [Prof. Jeremy Price](https://education.indianapolis.iu.edu/faculty-research/faculty-directory/price-jeremy.html), School of Education, Indiana University, as part of the [Faculty Assistance in Data Science – IU Research program](https://rdc.iu.edu/resource-catalog/faculty-assistance-data-science/) during Summer 2024, developing an analytics framework to quantify and visualize research impact.

Community-engaged research connects universities with communities to address social, educational, and policy challenges. While these collaborations produce meaningful outcomes, institutions often struggle to measure impact systematically—understanding how individual engagement components contribute to results, how activities interact, and how influence spreads over time.

### Project Overview

The CEnTR\*IMPACT framework provides a structured, quantitative approach to measure community-engaged research. It combines Bayesian updating, network-based modeling, and interactive visualizations to evaluate how engagement components align with research outcomes. By dynamically adjusting component weightings, the framework enables institutions to numerically assess how specific activities influence overall impact.

#### Key Highlights:
- Quantitative evaluation of inputs, outputs, and processes across 150 survey responses from 5 partner institutions
- Modeling ripple influence through network diffusion on 3-layer networks with 120+ nodes and 350 edges
- Survey-based alignment metrics producing posterior alignment scores with 95% confidence intervals
- Custom visualizations including solar correlation plots and spiral plots, summarizing 20 engagement dimensions
- Interactive dashboard enabling dynamic adjustment of 10+ component weightings to evaluate their effect on overall engagement outcomes

### Implementation

The project leveraged a cross-language tech stack to create an interactive and visually intuitive application:  

- Integrated R and Python with Streamlit using rpy2, allowing execution of R scripts dynamically within a web app.
- Developed multi-layer network simulations in Python and R, incorporating layer discounts and mutation models, enabling propagation analysis for 120+ participant nodes.
- Implemented Bayesian updating on survey-alignment metrics, producing posterior estimates for 20 engagement dimensions, reducing uncertainty in alignment scores by ~30% compared to raw survey means.
- Designed dynamic color mapping strategies across 10 color palettes, ensuring visual prominence for higher scores and intuitive interpretation of 200+ plotted nodes.
- Explored web scraping and NLP techniques to extract community engagement data, demonstrating capability to process hundreds of external data points for potential model expansion.

### Output

The deliverables included a fully functional Streamlit application that:  
- Rendered interactive visualizations directly from R and Python scripts, generating 30+ plots dynamically per user session  
- Provided actionable numeric metrics, including alignment scores, ripple effect propagation, and weighted impact measures  
- Enabled exploration of component weightings and their effect on overall engagement outcomes, allowing scenario testing for 10+ engagement strategies  
- Supported strategic decision-making through structured measurement of collaboration effectiveness, demonstrating quantifiable insights from qualitative partnership data  

<i>Skills: R, Python, Streamlit, rpy2, Bayesian Analysis, Network Modeling, Graph Theory, Data Visualization, Survey Analytics, Interactive Web Apps, Plotly, ggplot2</i>

### Repositories:
- [CEnTR-IMPACT](https://github.com/jeremyfprice/CEnTR-IMPACT) – Core IU framework for measuring community-engaged research.  
- [CEnTR-IMPACT Weightings](https://github.com/jeremyfprice/centr-impact-weightings) – Weighting and alignment calculation scripts.
- [CEnTR-IMPACT Visualizations](https://github.com/nehachede/FADS-Summer24) – Visualizations
- [The Open Science Framework - DOI](https://doi.org/10.17605/OSF.IO/TEG78)