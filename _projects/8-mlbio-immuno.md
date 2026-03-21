---
title: "Network-based machine learning approach to predict immunotherapy response in cancer patients"
collection: projects
permalink: /projects/8-ml-bio-immuno
excerpt: 'Developed a machine learning pipeline using NHANES data to identify health risk segments and predict disease outcomes. Applied PCA, clustering, association rule mining, and Random Forest classification, uncovering key drivers such as nutrition, cholesterol, and demographic factors.'
---

Health outcomes are influenced by a complex interplay of lifestyle, clinical, and socioeconomic factors. However, these relationships are often non-linear and difficult to interpret in isolation.

This project aims to build a data-driven framework to better understand these interactions and predict disease risk using the NHANES 2013–2014 dataset. The goal is not just prediction, but to uncover meaningful patterns that can support risk stratification, personalized care, and broader public health insights.

### Data Overview

The analysis uses NHANES, a nationally representative dataset that captures multiple dimensions of population health.

The dataset integrates:

- Demographics: age, gender, income, education
- Dietary intake: nutrient consumption, eating patterns
- Clinical measurements: BMI, blood pressure, body metrics
- Laboratory results: cholesterol, glucose, biomarkers
- Lifestyle factors: smoking, alcohol use, physical activity

This multi-dimensional structure enables a comprehensive view of how different factors interact to influence health outcomes.

<i>If you would like to explore or work with the data yourself, it is publicly available through the CDC: (NHANES 2013–2014 cycle)[https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023].</i>

### Analytical Approach

To capture both interpretability and predictive power, the analysis combines statistical techniques, unsupervised learning, and machine learning into a structured workflow.

<ol>
	<li> Discovering Relationships
<p>
The first step focused on identifying relationships across variables that may not be immediately visible.

- Continuous variables (e.g., BMI, blood pressure) were discretized into categorical bins
- Data was transformed into a format suitable for association analysis
- The Apriori algorithm was applied to identify frequent itemsets and generate association rules

This approach helped uncover co-occurring patterns between clinical conditions, medication usage, and physiological indicators, providing interpretable insights into how health factors interact.
</p>
	</li> 
	<li> Reducing Complexity and Segmenting Populations
<p>
Given the high dimensionality of the dataset, dimensionality reduction and clustering were used to structure the data more effectively.

- Principal Component Analysis (PCA) was applied to capture key variance drivers while reducing dimensionality
- Standardization and transformation techniques were used to ensure stability of the components
- Feature selection was further refined using correlation analysis and association-based filtering
- Using the transformed feature space, clustering was performed to group individuals into four distinct population segments.

Each cluster represented a unique combination of:

- Demographic characteristics (age, gender)
- Socioeconomic factors (income levels)
- Dietary patterns
- Clinical and physiological indicators

These segments highlight how risk is not uniform across populations, and reinforce the importance of stratified analysis.
</p>
	</li>
	<li>
	</li>
</ol>