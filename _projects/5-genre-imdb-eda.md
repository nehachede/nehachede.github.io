---
title: "Genre Fusion and More IMDb Film Ratings"
collection: projects
permalink: /projects/5-genre-imdb-eda
excerpt: "A data-driven study of how genre combinations, runtime, and release year shape IMDb ratings using 300K+ movies and GAM-based modeling."
---

### Introduction
Movie ratings on IMDb are often treated as simple indicators of success, but the factors behind them are far more complex. While genre is commonly assumed to influence ratings, films rarely belong to a single category, and combinations such as Comedy-Drama or Drama-Romance may shape audience perception differently.

This project investigates how genre fusion, runtime, and release year jointly influence IMDb ratings, and whether these relationships are linear or require more flexible modeling techniques. The goal is to move beyond descriptive statistics and understand how audience preferences evolve across time and cinematic styles.

#### Key Highlights
- Rating behavior is strongly non-linear across runtime and release year
- GAM significantly outperforms linear regression in explaining rating variation
- Drama is the most frequent genre (~47K films), followed by Documentary (~31K) and Comedy (~23K)
- Documentaries consistently achieve the highest ratings across all genres and production surged post-2000
- Hybrid genres (Comedy-Drama, Drama-Romance) outperform standalone Comedy by +0.4 to +0.6 rating
- Optimal runtime range for higher ratings: 120–180 minutes

## Data Overview
The dataset is sourced from IMDb and includes metadata and ratings information across films released between 1874 and 2024. It provides a unique opportunity to study how cinematic trends and viewer preferences have evolved over time, from early silent-era films to modern streaming-era productions.

We integrate two primary IMDb tables:

- title.basics.tsv: Contains metadata for each title, including release year, runtime, and genre classification.
- title.ratings.tsv: Contains user-driven feedback in the form of average ratings and number of votes per title.

The full dataset (Publicly available [here](https://datasets.imdbws.com/) spans 1874 to 2024, but the analysis is focused on modern cinematic patterns. To ensure meaningful and comparable trends, we apply the following filters:
- Only movies released after 1920 are included, capturing the era of modern cinema
- Only films with runtime ≤ 200 minutes are retained to remove extreme outliers (e.g., experimental or incomplete records)
- Entries with missing or invalid values in key fields (runtime, rating, or genre) are removed

After cleaning and filtering, the final dataset consists of approximately 300,000+ movies, providing a strong statistical base for analysis.

From the full dataset, we focus on the following variables:

- averageRating: IMDb user rating (1–10 scale), representing audience perception
- runtimeMinutes: Length of the movie, used to study engagement patterns
- startYear: Release year, used to capture historical trends
- genres: Multi-label genre classification (up to 3 genres per movie)
- numVotes: Number of user ratings, reflecting popularity and confidence in rating

### Approach
To understand how film characteristics influence audience reception, we analyzed IMDb data using a combination of exploratory data analysis, statistical aggregation, and regression modeling. The goal was to move beyond simple descriptive trends and identify how genre, runtime, and time period interact to shape movie ratings.

Due to the large number of unique genre combinations, analysis was restricted to the top five most frequent genres which represent both dominant categories and meaningful hybrid forms:
- Drama
- Documentary
- Comedy
- Comedy-Drama
- Drama-Romance

We perfomed Exploratory Data Analysis (EDA) to understand distributional and tempporal patterns in the data. 
- Genre frequency distribution
- IMDb rating distributions (boxplots)
- Temporal trends in movie production
- Rating evolution over decades
- Runtime bin analysis (0–60, 60–120, 120–180 minutes)

To model the relationship between film attributes and IMDb ratings, we first applied a Linear Regression model using runtime, release year and genre as predcitors:

$$
\text{Rating}_i = \beta_0 + \beta_1(\text{RuntimeMinutes}_i) + \beta_2(\text{StartYear}_i) + \sum_{k} \beta_k(\text{Genre}_{ik}) + \epsilon_i
$$

where genre was encoded using categorical indicator variables. This model served as a baseline under the assumption of linear relationships between predictors and ratings.

Given patterns observed during EDA, we extended the analysis using a Generalized Additive Model (GAM) to capture non-linear effects of continuous variables:

$$
\text{Rating}_i = \beta_0 + f_1(\text{RuntimeMinutes}_i) + f_2(\text{StartYear}_i) + \sum_{k} \beta_k(\text{Genre}_{ik}) + \epsilon_i
$$

where f
1
	​

 and f
2
	​

 are smooth functions estimated from the data. This formulation allowed the model to flexibly capture non-linear trends in ratings without imposing a fixed functional form.
---

### 3. Runtime and Rating Analysis
We examined how runtime influences ratings across genres:
- Documentaries remain consistently high-rated regardless of runtime
- Drama shows improved ratings with longer runtimes
- Comedy shows unstable and U-shaped trends in later years

---

### 4. Modeling Approach

#### Linear Regression (Baseline)
We first applied linear regression using:
- runtimeMinutes
- startYear
- genres

However, this model failed to capture non-linear patterns effectively.

---

#### Generalized Additive Model (GAM)
We applied GAM to model non-linear effects:

- s(runtimeMinutes)
- s(startYear)
- genres (categorical)

Key improvements:
- Better fit (higher R²)
- Lower AIC/BIC compared to LM
- Improved residual behavior
- Captures smooth temporal and runtime trends

---

### 5. Interaction Analysis (Contour Plots)
We further modeled:
- runtimeMinutes × startYear interaction per genre

Findings:
- Drama: higher ratings for longer films post-2000
- Documentary: consistently high ratings across years
- Comedy: unstable, with mid-century peak performance

---

## Key Takeaways and Conclusion
- Documentaries consistently outperform all genres in IMDb ratings.
- Genre combinations (Comedy-Drama, Drama-Romance) generally outperform single genres like Comedy.
- Runtime plays a significant but genre-dependent role in rating outcomes.
- Audience preferences have shifted significantly over time, especially post-2000.
- GAM models are more effective than linear regression in capturing real-world rating behavior.
- Comedy shows the most variability and weakest overall performance.

---

## Future Directions
- Incorporate director and actor-level influence on ratings
- Analyze number of votes as a confidence-weighted factor in rating reliability
- Extend analysis to streaming-era data post-2020
- Explore sentiment analysis of reviews alongside ratings
- Build predictive models for IMDb rating forecasting
- Investigate genre evolution using clustering techniques

---

## Explore the full project on
[GitHub Repository](https://github.com/your-repo-link-here)

---

<i>Tech Stack:</i> R, ggplot2, dplyr, mgcv (GAM), caret, tidyverse, data visualization, statistical modeling, IMDb datasets