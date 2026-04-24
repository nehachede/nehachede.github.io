---
title: "Deciphering Customer Reviews"
collection: projects
permalink: /projects/6-adj-analysis
excerpt: 'Built an end-to-end NLP pipeline using MongoDB and PySpark to extract sentiment patterns from e-commerce reviews through adjective-driven analysis and linguistic feature engineering.'
---

### Introduction
The rapid growth of e-commerce has led to an abundance of customer reviews, yet most analysis relies heavily on numerical ratings, overlooking the richness of textual feedback. Ratings alone often fail to capture why customers feel satisfied or dissatisfied.

This project addresses that gap by building a scalable pipeline to analyze how customers describe products, using adjectives as high-signal indicators of sentiment. By integrating data engineering, distributed systems, and NLP, the project transforms raw review text into interpretable patterns that reveal deeper insights into customer experience.

#### Key Highlights
- Processed 10,000+ product records with semi-structured attributes
- Engineered structured features from hierarchical categories and inconsistent price formats
- Handled ~14% missing price data using hierarchical, category-based imputation
- Built a cloud-backed pipeline using MongoDB Atlas + PySpark integration
- Extracted sentiment-driving features using POS tagging (NLTK)
- Improved NLP accuracy by removing noise via spaCy NER (entity filtering)
- Identified clear linguistic differences between high vs low rating reviews

### Data Overview
The dataset, sourced from data.world (PromptCloud), contains product-level information along with customer-generated reviews. It includes structured attributes such as product name, manufacturer, price, and rating, as well as unstructured text fields like customer reviews and product descriptions.

To enable analysis across multiple dimensions, the dataset was transformed into a structured format:

- Hierarchical product categories were split into five separate categorical features
- Review ratings were converted from string format (e.g., “4.5 out of 5 stars”) into numeric values
- Price data was standardized:
	- Currency symbols removed
	- Price ranges converted to mean values
- Stock availability was decomposed into:
	- Quantity (numeric)
	- Condition (categorical: new, used, refurbished)

A key challenge was handling missing values, particularly in the price column (~1435 records). Instead of applying global imputation, a hierarchical strategy was used:

- Primary: Mean price within Category Level 1 + Category Level 2
- Secondary: Mean price within Category Level 1

This preserved category-level pricing behavior and reduced distortion in downstream analysis.

### Analytical Approach
The project followed a multi-stage pipeline combining preprocessing, linguistic feature extraction, and visualization.

Cleaned data was first stored in MongoDB Atlas, enabling flexible schema handling and remote accessibility. Using the MongoDB Spark Connector, data was accessed through PySpark, allowing integration with distributed processing workflows.

The NLP pipeline focused on extracting meaningful linguistic signals from customer reviews:

- Preprocessed text by removing punctuation, stopwords, numeric tokens, and low-signal terms
- Tokenized reviews using NLTK
- Filtering out low-information terms (e.g., months, common filler words)
- Identified adjectives via part-of-speech tagging (JJ tags)

Initial word frequency analysis revealed that commonly occurring terms were often generic (e.g., “product”, “item”), limiting their usefulness for sentiment interpretation. To address this, the analysis shifted toward adjective extraction, leveraging part-of-speech tagging:

- Extracted adjectives using NLTK POS tagging (JJ tags)
- Aggregated adjective frequencies across rating categories

However, the model initially misclassified proper nouns (e.g., reviewer names) as adjectives. To improve accuracy, spaCy’s Named Entity Recognition (NER) was applied to filter out person entities, ensuring that only descriptive terms were retained. The refined dataset enabled comparative analysis across rating groups, supported by:

Frequency distributions of top adjectives
Side-by-side comparison of high vs low rating descriptors
Word cloud visualization for highly rated products

### Key Takeaways & Conclusions
The analysis revealed distinct and interpretable patterns in how customers express sentiment through language.

- Low-rated reviews frequently included adjectives such as “poor”, “flimsy”, and “large”, indicating dissatisfaction related to product quality and unmet expectations
- High-rated reviews were dominated by “great”, “excellent”, “perfect”, and “nice”, reflecting strong customer satisfaction and alignment with expectations

An interesting observation was the presence of moderately positive terms like “good” across both high and low ratings. This suggests that customer sentiment is often multi-dimensional, where users may acknowledge certain positive aspects despite an overall negative experience.

From a methodological perspective, the project highlights that:

- Adjectives serve as high-signal linguistic features for sentiment interpretation
- Data preprocessing and noise reduction significantly impact NLP output quality
- Combining structured data engineering with unstructured text analysis enables richer insights than either approach alone

### Future Directions
- Extend analysis to sentiment classification models (positive, negative, neutral)
- Implement aspect-based sentiment analysis to link adjectives with specific product features
- Apply sentiment intensity scoring using models such as VADER or transformer-based approaches
- Enhance seller-level analysis by fully structuring nested JSON data
- Scale the pipeline using fully distributed Spark-based processing

Explore the full project on [GitHub](https://github.com/nehachede/Customer-Reviews-Sentiment-Analysis).

<i>Tech Stack: Python, Pandas, NumPy, PySpark, MongoDB, NLTK, spaCy, Matplotlib, Seaborn, WordCloud, Data Preprocessing, Feature Engineering, Natural Language Processing, Text Analytics, Sentiment Analysis, Distributed Computing</i>