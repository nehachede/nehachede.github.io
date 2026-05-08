---
title: "Economic Convergence: An Analysis of Global GDP Growth"
collection: projects
permalink: /projects/4-gdp-growth-eda
excerpt: 'Analyzed 60 years of global GDP per capita data to evaluate economic convergence patterns across countries, continents, and historical periods using statistical analysis and visualization in R.'
---

### Introduction
Economic convergence is the hypothesis that poorer countries tend to grow faster than richer ones, leading to a reduction in global income disparities over time, though empirical evidence is mixed and context-dependent. This project explores whether this pattern is observed in global GDP per capita data from 1960–2019, and how growth and convergence differ across countries, continents, and historical periods.

### Key Highlights
- Analyzed 60 years of GDP per capita data across 190+ countries.
- Calculated annualized GDP growth rates to identify the fastest- and slowest-growing economies globally.
- Examined convergence trends between poorer and richer countries using correlation analysis
- Compared economic growth patterns across Asia, Africa, Europe, the Americas, and Oceania.
- Analyzed convergence behavior across multiple periods: 1960–1980, 1980–2000, and 2000–2019
- Built comparative visualizations to evaluate regional economic performance and disparities
- Identified economic, political, and structural factors influencing growth disparities across regions.

### Data Overview
The project uses publicly available datasets from Gapminder, including:
- GDP per capita data (inflation-adjusted)
- Population data
- Country-to-continent mapping
The datasets were cleaned, merged, and transformed to support continent-level and country-level growth analysis.
- Filtered GDP data for the period 1960–2019.
- Joined economic data with continent mappings for regional analysis.
- Handled missing values and inconsistent observations.

### Approach

Annualized GDP growth rates were calculated using compound annual growth formulas to identify the fastest- and slowest-growing economies over the six-decade period. 
- Calculated annual GDP per capita growth rates for each country between 1960 and 2019
- Ranked countries to identify the fastest-growing and slowest-growing economies globally
- Merged country-level economic data with continent classifications for regional analysis
- Built comparative visualizations to examine long-term growth distributions and disparities
To evaluate economic convergence:
- Tested relationship between 1960 GDP per capita and long-term growth using correlation analysis
- Used scatter plots to assess whether lower-income countries grew faster over time
- Extended analysis to continent-level comparisons (Asia, Africa, Europe, Americas, Oceania)
The study was further extended across three historical periods — 1960–1980, 1980–2000, and 2000–2019 — to understand how convergence dynamics evolved over time and whether globalization and economic reforms accelerated growth in lower-income economies. To assess changes over time:
- Split analysis into three periods: 1960–1980, 1980–2000, 2000–2019
- Recomputed growth rates and correlation coefficients for each period
- Compared regional convergence patterns across decades to identify structural shifts in growth dynamics

### Key Takeaways and Conclusion
The results suggest that convergence is not automatic and depends heavily on economic structure, governance, and access to global markets rather than initial income alone.
- Asian economies show the strongest convergence patterns, with several countries transitioning from low-income to high-growth trajectories driven by industrialization, globalization, and policy reforms
- African countries show weak or inconsistent convergence, largely influenced by political instability, resource dependency, and infrastructure limitations
- The Americas show moderate convergence, with mixed growth performance across countries
- Europe and Oceania exhibit weaker convergence signals, as many countries were already high-income in 1960 and experienced more stable, slower growth

### Future Steps
- Extend analysis using PPP-adjusted and inflation-adjusted GDP per capita for improved comparability.
- Incorporate additional macroeconomic indicators such as inflation, trade openness, education expenditure, and HDI.
- Apply regression modeling and causal inference techniques to quantify drivers of convergence.
- Explore clustering methods to group countries based on growth trajectories.
- Extend the analysis using World Bank or IMF datasets for deeper economic benchmarking.

Explore the full project on [GitHub](https://github.com/nehachede/Economic-Convergence-GDP-growth-analysis-R).

### <i>Tech Stack</i>
R • tidyverse • dplyr • ggplot2 • readr • Statistical Analysis • Exploratory Data Analysis (EDA) • Data Visualization • Correlation Analysis • Economic Data Analysis