---
title: "Predicting Health Outcomes using Nutritional Intake, Socioeconomic factors and Sleep Data"
collection: projects
permalink: /projects/7-health-outcomes-pred-DM
excerpt: 'Developed a multi-stage machine learning pipeline on NHANES data integrating association rule mining, PCA-based clustering, and Random Forest classification to predict disease-linked medication usage and identify latent health patterns.'
---


The increasing availability of population-scale health data presents an opportunity to move beyond isolated statistical analyses toward integrated, data-driven modeling of health outcomes. However, relationships across clinical, behavioral, and socioeconomic variables are often high-dimensional, non-linear, and difficult to interpret in isolation.

This project develops a multi-stage machine learning framework to systematically uncover latent structure in population health data and predict disease-linked outcomes using the NHANES 2013–2014 dataset. The objective is not only predictive accuracy, but also interpretability—identifying meaningful health segments and the underlying drivers that define them.

#### Key highlights

The proposed framework combines unsupervised learning, association rule mining, and supervised classification to model interactions across multiple dimensions of health.

- Integrated 6 NHANES data modalities into a unified dataset of ~2,000 individuals and 70+ features
- Identified strong co-occurrence patterns across chronic condition indicators using association rule mining (confidence up to 0.91, lift > 1)
- Reduced dimensionality while preserving 95% variance
- Discovered 4 distinct health segments using K-Means clustering with optimized cluster selection
- Built a Random Forest classifier achieving ~65% accuracy on multi-class medication prediction
- Identified key predictive drivers including sugar intake, cholesterol levels, micronutrients, and demographic variables.

### Data Overview

The analysis uses NHANES, a nationally representative dataset that captures multiple dimensions of population health.

The dataset integrates:

- Demographics: age, gender, race, income, education
- Dietary: nutrient consumption, eating patterns
- Examination: BMI, blood pressure, body metrics
- Laboratory: cholesterol, glucose, biomarkers
- Medications: prescription, diagnosis
- Questionnaire: smoking, alcohol use, physical activity

To create a multi-modal representation of each individual and ensure analytical consistency:

- Missing values were imputed using mean-based strategies to preserve sample size
- Categorical variables were one-hot encoded to enable downstream modeling
- Numerical features were standardized to align scales across domains
- Highly skewed variables (e.g., cholesterol, micronutrients) were transformed using Box-Cox

<i>If you would like to explore or work with the data yourself, it is publicly available through the CDC: [NHANES 2013–2014 cycle](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023).</i>

### Analytical Approach

To reveal patterns in chronic disease risk and capture both interpretability and predictive power, the analysis followed a four-step pipeline, integrating unsupervised leardning, association analysis and supervised prediction.

We first explored co-occurrence of health conditions using association rule mining. By recoding categorical outcomes and binning continuous variables, we discovered that:

- Diabetes and hepatitis frequently co-occurred, with a support of 74.4% and confidence of 85.6%  
- Asthma was strongly associated with diabetes and hepatitis, highlighting potential compounded risk  

These associations informed our feature selection for subsequent analysis, ensuring critical health-related variables were retained.  

Next, Principal Component Analysis (PCA) reduced the dataset's dimensionality while retaining 95% of the variance. Height, age, income-to-poverty ratio, potassium and phosphorus intake, and white blood cell count emerged as dominant contributors. This step revealed latent patterns across demographics, nutrition, and biomarkers, highlighting underlying factors influencing chronic disease risk.  

We then applied K-Means clustering to identify natural population groupings. The optimal solution of four clusters revealed distinct profiles:

- Cluster 0: Taller individuals with moderate nutrient intake, representing a specific demographic  
- Cluster 1: Shorter height, lower potassium intake, notable military presence  
- Cluster 2: Younger, pregnant individuals with moderate WBC counts  
- Cluster 3: Taller, ethnically diverse, high phosphorus and carbohydrate intake  

Finally, we trained a Random Forest classifier to predict chronic disease risk. A baseline model achieved 65% accuracy but underperformed on minority classes. Introducing class balancing maintained overall accuracy while improving recall and F1-scores for underrepresented categories. 
Key predictive features included sugar intake, total cholesterol, calcium, vitamin B6, saturated fat, and HDL cholesterol, confirming the importance of dietary habits and metabolic markers in chronic disease risk.

### Key Takeaways & Conclusions

- Multi-modal analysis uncovered hidden patterns in chronic disease risk, emphasizing links between diabetes, asthma, and hepatitis.
- PCA identified dominant contributors such as height, age, and nutrient intake, reducing dimensionality while retaining variance.  
- Clustering revealed four actionable risk groups, enabling population-level insights  
- Random Forest classification validated clusters and highlighted key predictors for personalized interventions.
- Integrating association rules, PCA, clustering, and classification provided a robust framework for health outcome prediction.

### Future Directions
- Incorporate longitudinal NHANES or time-series data for dynamic risk modeling  
- Explore advanced ML algorithms (Gradient Boosting, Neural Networks)
- Apply advanced methods like SMOTE to address class imbalance
- Expand features to include genetic markers and additional health data

Explore the full project on [GitHub](https://github.com/nehachede/Health-Outcomes-Prediction/tree/main).

<i>Tech Stack: Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, PCA, K-Means Clustering, Random Forest, Association Rule Mining, Box-Cox Transformation, Data Preprocessing, Feature Engineering, Statistical Analysis, Data Visualization</i>