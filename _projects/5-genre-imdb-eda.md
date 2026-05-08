---
title: "Genre Fusion and More IMDb Film Ratings"
collection: projects
permalink: /projects/5-genre-imdb-eda
excerpt: "Analyzed 300K+ IMDb films to study how genre combinations, runtime, and release year shaped audience ratings through non-linear modeling and Generalized Additive Models (GAM)."
---

### Introduction
Movie ratings on IMDb are often treated as simple indicators of success, but the factors behind them are far more complex. While genre is commonly assumed to influence ratings, films rarely belong to a single category, and combinations such as Comedy-Drama or Drama-Romance may shape audience perception differently.

This project investigates how genre fusion, runtime, and release year jointly influence IMDb ratings, and whether these relationships are linear or require more flexible modeling techniques. The goal is to move beyond descriptive statistics and understand how audience preferences evolve across time and cinematic styles.

#### Key Highlights
- GAM significantly outperforms linear regression in explaining rating variation
- Documentaries achieve the highest ratings across all genres
- Genre combinations (Comedy-Drama, Drama-Romance) outperform standalone Comedy
- Optimal runtime range for higher ratings: 120–180 minutes
- Ratings exhibit strong non-linear patterns across runtime and release year

### Data Overview
The dataset is sourced from IMDb (Publicly available [here](https://datasets.imdbws.com/)) and includes metadata and ratings information across films released between 1874 and 2024. 

- title.basics.tsv: Contains metadata for each title, including release year, runtime, and genre classification.
- title.ratings.tsv: Contains user-driven feedback in the form of average ratings and number of votes per title.

To ensure meaningful and comparable trends, we filtered resulting in a final sample of 300,000_ movies:
- Only movies released after 1920 are included, capturing the era of modern cinema
- Only films with runtime ≤ 200 minutes are retained to remove extreme outliers (e.g., experimental or incomplete records)
- Entries with missing or invalid values in key fields (runtime, rating, or genre) are removed
The final dataset consists of approximately 300,000+ movies.
### Approach
To understand how film characteristics influence audience reception, we analyzed IMDb data using a combination of exploratory data analysis, statistical aggregation, and regression modeling. The goal was to move beyond simple descriptive trends and identify how genre, runtime, and time period interact to shape movie ratings.

We perfomed Exploratory Data Analysis (EDA) to understand distributional and tempporal patterns in the data. 
- Selected top genres: Drama, Documentary, Comedy, Comedy-Drama, Drama-Romance.
- Runtime binning revealed that films in the 120–180 minute range achieved the highest average ratings (~7.0+), while short films (<60 min) underperformed (~6.2–6.5)

We first applied a Linear Regression model using runtime, release year and genre as predcitors:

$$
\text{Rating}_i = \beta_0 + \beta_1(\text{RuntimeMinutes}_i) + \beta_2(\text{StartYear}_i) + \sum_{k} \beta_k(\text{Genre}_{ik}) + \epsilon_i
$$

where genre was encoded using categorical indicator variables. This model served as a baseline under the assumption of linear relationships between predictors and ratings and achieved $$R^2$$ ≈ 0.1659 and $$RMSE$$ ≈ 1.17. Residual diagnostics showed structured patterns, particularly across runtime bins and release years, indicating violation of linearity assumptions confirming the non-linear patterns observed with EDA.

We extended the analysis using a Generalized Additive Model (GAM) to capture non-linear effects of continuous variables:

$$
\text{Rating}_i = \beta_0 + f_1(\text{RuntimeMinutes}_i) + f_2(\text{StartYear}_i) + \sum_{k} \beta_k(\text{Genre}_{ik}) + \epsilon_i
$$

where $$f_{1}$$ and $$f_{2}$$ are spline-based smooth functions estimated from the data. Model performance improved to $$R^2$$ ≈ 0.177 for unweighted GAM and $$R^2$$ ≈ 0.344 for weighted specification. $$RMSE$$ reduced to ≈ 1.16.

Key model improvements over Linear Regression:
- GAM increased explained variance
- Residual standard error decreased indicating tighter fit
- `AIC`/`BIC` improved consistently across all specifications
- Residual plots showed reduced systematic bias compared to LM, though mild heteroscedasticity remained at rating extremes

While weighted models using vote counts were considered, they were excluded to avoid introducing additional bias and complexity, ensuring interpretability and consistency across models.

We further modeled two-dimensional interaction surfaces using a Generalized Additive Model (GAM). Instead of treating runtime and release year independently rather than assuming additive or linear relationships, we fit a smooth interaction term:

$$
s(\text{runtimeMinutes}, \text{startYear})
$$

### Key Takeaways and Conclusion
- GAM provides better fit than linear regression for rating prediction
- Runtime plays a significant but genre-dependent role in rating outcomes
- Documentaries consistently outperform all genres in IMDb ratings
- Comedy shows the highest variance and weakest consistency
- Audience preferences have shifted significantly over time, especially post-2000
- Interaction analysis revealed that rating behavior evolves over time, particularly for Drama, where longer films have become more favorably rated in recent decades

### Future Directions
- Incorporate director and actor-level influence on ratings
- Extend analysis to streaming-era data post-2020
- Sentiment analysis of reviews alongside ratings
- Build predictive models for IMDb rating forecasting
- Investigate genre evolution using clustering techniques

Explore the full project on [GitHub](https://github.com/nehachede/IMDb-Ratings-Genre-Fusion-GAM-Analysis).

<i>Tech Stack: R, ggplot2, dplyr, mgcv, caret, tidyverse, linear regression, generalized additive models (GAM), data visualization, statistical modeling</i>