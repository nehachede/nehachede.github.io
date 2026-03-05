---
title: "Metrics and Visual Analytics for Community-Engaged Research"
collection: projects
permalink: /projects/8-community-research-metrics-visualization
excerpt: "Designed a data-driven framework to quantify and visualize community-engaged research impact using network analysis, Bayesian updating, and advanced R-based visualizations."
---

In Spring 2024, I worked on a data science project focused on **developing quantitative metrics and visual analytics to evaluate Community-Engaged Research (CEnR)**. The goal was to create scalable methods to measure collaboration quality, partner alignment, and potential research impact using data from research teams and community partners.

The project explored how **statistical modeling, network analysis, and visualization techniques** can transform qualitative collaboration data into interpretable metrics that help institutions better understand the effectiveness and reach of community partnerships.

Using **R, Python, and graph-based methods**, I built a prototype analytical pipeline that computed alignment scores, modeled ripple influence across networks, and generated visual representations of collaboration dynamics.

Key components of the work included:

- **Bayesian updating models** to adjust research-team alignment scores using partner feedback collected through Likert-scale surveys.
- **Network analysis using graph theory** to model potential ripple influence of research outputs across three degrees of separation.
- **Node importance metrics** combining diffusion degree and PageRank to quantify influence within collaboration networks.
- **Custom impact scoring framework** incorporating layer-based weighting to estimate overall project influence.
- **Advanced visual analytics** including Solar Correlation Maps (spiral plots), spider/radar plots, and radial statistical plots to communicate multidimensional metrics.

Several visualization techniques were implemented to help stakeholders interpret complex relationships:

**Solar Correlation Map (Archimedean Spiral)**  
Nodes represent evaluation categories such as goals, roles, resources, and outcomes, while radial distance and node size represent alignment scores and relative importance.

**Spider / Radar Plot**  
Used to compare alignment scores across key collaboration dimensions including goals, processes, outputs, and empowerment.

**Radial Statistical Impact Plot**  
Displays normalized project impact scores across multiple research engagement dimensions.

The analytical workflow integrated:

- **R statistical computing** for modeling, survey analysis, and visualization  
- **Python and NetworkX** for graph-based modeling  
- **igraph and centiserve** for network centrality metrics  
- **ggplot2 and ggforce** for custom radial and spiral visualizations  
- **rpy2 integration** enabling Python–R interoperability for flexible analytics pipelines

The final system demonstrated how **collaboration quality, alignment, and community impact can be quantified and visualized**, making it easier for research organizations to evaluate and improve their community-engaged initiatives.

This project strengthened my experience in **data modeling, statistical computing, network analytics, and scientific visualization**, while exploring how data science can support **evidence-based evaluation of research partnerships**.

**Project Type:** Group Project  
**Output:** Analytical framework + interactive visualizations + statistical modeling pipeline  

**Skills:**  
R · Python · Network Analysis · Bayesian Updating · Graph Theory · Data Visualization · ggplot2 · igraph · NetworkX · Statistical Modeling

**GitHub:**  
https://github.com/nehachede/INFO-I-590-Data-Viz-Group-Project-Fall24