---
layout: archive
title: "Work Experience"
permalink: /work/
author_profile: true
---

{% include base_path %}

I am a dedicated Data Scientist with a Master’s in Data Science and 5+ years of experience delivering data-driven insights through statistical modeling, machine learning, and real-world data (RWD) analysis. I specialize in healthcare and biopharma analytics, building scalable data pipelines, forecasting models, and business intelligence solutions that support evidence-based decision-making and operational efficiency.

I am proficient in Python, R, SQL, SAS, Power BI, and Tableau, with a strong track record of automating workflows, improving data quality, and translating complex datasets into actionable strategy. I was recognized with multiple SPOT awards and an Impact award at Mu Sigma for exceeding project goals, delivering measurable results, and leading high-performing analytics initiatives. I am currently seeking full-time opportunities where I can leverage my analytical, technical, and problem-solving skills to drive meaningful impact in dynamic, data-driven environments.

{% for post in site.work reversed %}
  {% include archive-single.html %}
{% endfor %}