---
title: "The Power of Lyrics"
collection: projects
permalink: /projects/3-sentiment-analysis-viz
excerpt: 'Investigated the relationship between lyrical complexity, emotional tone, and song popularity using NLP techniques on ~60,000 song lyrics and Spotify streaming data.'
---

### Introduction

Music streaming platforms like Spotify have transformed how we consume and evaluate music, generating massive datasets that capture both listening behavior and song characteristics. While most existing research focuses on acoustic features such as tempo, energy, and rhythm, the role of lyrics remains comparatively underexplored.
This project investigates whether lyrical complexity and emotional tone influence song popularity and analyzes whether more readable, emotionally charged, or linguistically rich lyrics correlate with higher streaming performance.

### Key Highlights
- Analyzed ~60,000 song lyrics combined with 3M+ Spotify streaming records
- Studied relationship between lyrical complexity, emotional tone and song popularity
- Applied NLP techniques to extract structured meaning from lyrics
- Discovered weak relationship between lyrical complexity and popularity

### Data Overview
This project combines 2 large-scale datasets to connect lyrics with real-world streaming behaviour: 
- Spotify streaming dataset (tracks, artists, streams, regions)
- Lyrics Dataset (lyrics and metadata)
For reliable analysis, the data was cleaned and standardized:
- Standardized artist and song names (lowercasing, trimming spaces)
- Removed missing values in key fields (track name, artist, URLs)
- Merged datasets using exact artist + song matching
- Cleaned lyrics by:
	- Removing annotations (e.g., [Chorus], [Verse])
	- Removing punctuation and special characters
	- Tokenizing and lemmatizing words
	- Removing stopwords for meaningful text extraction

### Analytical Approach
The analysis was structured as an NLP-driven exploration of how lyrical characteristics relate to song popularity on Spotify.
- Engineered textual features from lyrics to quantify readability and complexity, enabling numerical comparison across songs
- Used readability metrics such as Flesch Reading Ease and Gunning Fog Index to represent linguistic difficulty
- Computed lexical diversity to capture vocabulary richness and variation within lyrics

To understand listening behavior patterns:
- Aggregated stream counts across tracks, artists, and regions to identify dominant consumption trends
- Ranked songs and artists to highlight global popularity patterns and long-tail distribution in streaming data
- Visualized geographic streaming distribution to compare regional engagement levels
- Engineered region-to-country mappings and integrated `GeoJSON` data for global choropleth visualizations of streaming distribution

To analyze emotional content in lyrics:
- Applied sentiment analysis using TextBlob to extract polarity (emotional direction)
- Measured subjectivity to quantify emotional expression in lyrics
- Compared sentiment distributions across high- and low-popularity songs

To evaluate relationships between lyrics and popularity:
- Performed correlation analysis between lyrical features and stream counts
- Observed consistently weak correlations (≈ -0.04) between readability metrics and streams
- Identified strong inverse relationship between readability metrics themselves (Flesch vs Gunning Fog ≈ -0.99), validating metric consistency
- Used scatter plots to examine whether any nonlinear patterns existed between complexity and popularity

To assess predictive power:
- Built a linear regression model using lyrical features to predict stream counts
$$
\text{Streams} = \beta_0 + \beta_1(\text{Flesch Reading Ease}) + \beta_2(\text{Gunning Fog Index}) + \beta_3(\text{Lexical Diversity})
$$
- Evaluated model performance using error metrics and residual analysi
- Model predictions showed poor alignment with actual stream values, indicating that lyrical features alone are insufficient predictors of song popularity

### Key Takeaways & Conclusion
- Lyrical complexity (readability, vocabulary richness, and structural difficulty) shows very weak correlation with song popularity  
- Emotional tone shows a slightly stronger signal, where moderately positive sentiment tends to align with higher streams  
- Streaming behavior is highly skewed, with a small number of artists accounting for a large share of total streams  
- Predictive modeling confirms that lyrics alone are insufficient to explain streaming success  
- Overall, song popularity is likely driven more by external factors such as artist reputation, genre, production quality, and recommendation systems than by lyrical structure  

### Future Scope
- Integrate audio features (tempo, energy, danceability) to build a multimodal popularity prediction model  
- Apply transformer-based NLP models (e.g., BERT) to capture deeper semantic meaning in lyrics  
- Extend analysis across genres to evaluate whether lyrical impact varies by music style  
- Incorporate external signals such as playlists, social media trends, and user engagement data  
- Perform time-based analysis to study how lyrical trends evolve across different music eras

Explore the full project on [GitHub](https://github.com/nehachede/lyrical-complexity-vs-popularity-nlp).

<i>Tech Stack: Python, Pandas, NumPy, Scikit-learn, NLTK, TextBlob, Textstat, Matplotlib, Seaborn, Plotly, Altair, WordCloud, GeoJSON, SciPy</i>