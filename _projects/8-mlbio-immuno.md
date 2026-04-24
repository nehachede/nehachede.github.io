---
title: "Network-based machine learning approach to predict immunotherapy response in cancer patients"
collection: projects
permalink: /projects/8-ml-bio-immuno
excerpt: "Extended a network-based ML framework using protein-protein interaction networks and NetBio biomarkers to predict immunotherapy response. Evaluated XGBoost and deep learning models against logistic regression using LOOCV on imbalanced clinical datasets."
---

### Introduction
Immune checkpoint inhibitors (ICIs) have transformed cancer treatment by enabling the immune system to recognize and attack tumor cells more effectively. Despite their success, only ~30% of patients with solid tumors respond to immunotherapy, while others experience little benefit or adverse effects.  

This creates a critical need for predictive biomarkers that can identify likely responders before treatment begins. Traditional gene-based approaches often fail to capture the complex biological interactions underlying treatment response.  

This project builds on a network-based machine learning framework, leveraging protein-protein interaction (PPI) networks and pathway-level biomarkers (NetBio) to better model these interactions. We extend prior work by evaluating XGBoost and deep learning architectures to improve prediction of immunotherapy response.

---

### Data Overview
The study integrates multiple public datasets containing ICI-treated patient cohorts, including Kim et al., TCGA, IMvigor210, and others across cancer types such as melanoma, gastric, and bladder cancer.  

- PPI Network (STRING):  
  - ~16,597 nodes and 420,381 edges  
  - Captures gene-gene interactions for network-based feature construction  

- Patient Data:  
  - Treatment response (Responder vs Non-responder)  
  - Survival and progression outcomes  
  - Derived from multiple clinical studies  

- Biomarker Categories:  
  - NetBio: Network-based pathway biomarkers (primary feature set)  
  - GeneBio: Gene-level markers (e.g., PD-1, PD-L1, CTLA4)  
  - TME-Bio: Tumor microenvironment features (CD8 T cells, CAFs, T-cell exhaustion)  

The primary experimental dataset (Kim et al.) consisted of 45 gastric cancer patients, with class imbalance reflecting real-world response rates (~30% responders).

---

### Methodology
The approach follows a network-driven ML pipeline, beginning with biomarker construction and extending into predictive modeling.

We first leveraged the STRING PPI network to identify genes proximal to immune checkpoint targets using the PageRank algorithm, capturing network influence beyond individual genes. Pathway enrichment was then validated using hypergeometric testing, ensuring biological relevance of selected NetBio features.  

Using these features, we trained multiple machine learning models to classify patients into responders and non-responders.

The baseline Logistic Regression model, as proposed in the original study, achieved 60–80% accuracy across datasets, demonstrating the effectiveness of NetBio features over traditional biomarkers.  

We extended this framework with additional models:

- XGBoost (gradient-boosted trees):  
  Designed to improve upon Random Forest by learning from residual errors  
- Deep Neural Network (DNN):  
  Explored non-linear relationships with hyperparameter tuning  
- Recurrent Neural Network (RNN):  
  Tested for sequential and interaction-based feature learning  

All models were evaluated using Leave-One-Out Cross Validation (LOOCV) due to the small dataset size.

### Key observations from experiments

- XGBoost consistently outperformed DNN and RNN, showing stronger generalization on small datasets  
- Deep learning models underperformed due to limited sample size (n=45) and sensitivity to class imbalance  
- Logistic Regression remained highly competitive, particularly on combined biomarker sets (e.g., TME-Bio)  
- Accuracy alone was misleading due to imbalance (baseline ~27% random accuracy), making F1-score a critical metric 
- Models often biased toward the majority class (non-responders), even with class weighting  
- F1-score analysis revealed that performance gains were incremental rather than transformative  

Overall, results confirmed that:

- NetBio features improve predictive performance compared to GeneBio and TME-based biomarkers 
- Advanced models (XGBoost, DNN, RNN) did not significantly outperform Logistic Regression under current constraints  

---

### Key Takeaways & Conclusion
- Network-based biomarkers (NetBio) provide a stronger representation of biological interactions than gene-level features  
- Logistic Regression remains a robust baseline for small, high-dimensional biomedical datasets  
- XGBoost showed the most promise among advanced models but was limited by dataset size  
- Deep learning models require larger datasets to outperform traditional approaches  
- Class imbalance significantly impacts performance, making F1-score and recall essential evaluation metrics  
- Predicting immunotherapy response remains a challenging but high-impact problem, with clear opportunities for improvement  

---

### Future Directions
- Expand dataset size using multi-cohort integration to improve model generalization  
- Apply SMOTE or advanced resampling techniques to address class imbalance  
- Explore transfer learning across cancer types to improve cross-study prediction  
- Incorporate multi-omics data (genomics, transcriptomics) for richer feature representation
- Investigate graph neural networks (GNNs) to directly model PPI network structure  
- Improve reproducibility by standardizing pipelines and resolving dataset inconsistencies  

---

Explore the full project on [GitHub](https://github.com/nehachede/Predict-IO-Response-NetworkML).

---

Skills: Python, Scikit-learn, XGBoost, Deep Learning, Neural Networks, RNN, Logistic Regression, Network Biology, Protein-Protein Interaction Networks, Feature Engineering, LOOCV, Model Evaluation, ROC Analysis, F1 Score, Class Imbalance Handling, Biomedical Data Analysis