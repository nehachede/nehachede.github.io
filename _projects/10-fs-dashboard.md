---
title: "Hoosier Uplands Data Library - Food Security Dashboard"
collection: projects
permalink: /projects/10-fs-dashboard
excerpt: "Collaborated on building an automated data pipeline and Tableau dashboard analyzing food access across 11 Indiana counties, integrating data from 15+ fragmented sources and 70 food assistance providers to identify geographic service gaps and accessibility barriers."
---

This project developed a data-driven dashboard to analyze food accessibility across the Hoosier Uplands region of Indiana, addressing the challenge of fragmented food security data across multiple agencies and organizations. Working as part of a team, we consolidated data from public directories, county offices, food banks, WIC programs, school meal listings, and nonprofit organizations to create a unified dataset supporting community planning and outreach.

### Data Integration & Pipeline

Data was collected from 15+ fragmented sources, including county DFR offices, regional food banks, nonprofit directories, faith-based organizations, and government websites. Automated Python web scraping pipelines using BeautifulSoup and Selenium extracted organization-level data such as service types, operating hours, eligibility criteria, geographic coordinates, and contact information.

The cleaned dataset was validated and stored in Google BigQuery, with additional preprocessing performed in Python to standardize inconsistent formats, parse operating schedules, and derive structured analytical features such as weekday availability flags and total weekly operating hours.

Final dataset coverage:

* 11 Indiana counties (Crawford, Daviess, Dubois, Jackson, Lawrence, Martin, Monroe, Orange, Perry, Scott, Washington)
* 87 ZIP codes analyzed
* 70 unique food assistance providers
* 48 structured data attributes per organization

### Dashboard & Analytical Framework

An interactive Tableau dashboard was developed to help stakeholders explore service distribution, accessibility patterns, and operational characteristics of food assistance providers across the region. The dashboard provides four analytical views:

* Geographic coverage: provider distribution and ZIP-level service gaps
* Providers & service types: diversity and availability of food assistance services
* Eligibility analysis: populations served and access restrictions
* Funding patterns: financial support structures and sustainability indicators

### Key Insights & Impact

Analysis of the consolidated dataset revealed several important patterns in regional food access:

* Only 31% of ZIP codes across the 11-county region have at least one food provider.
* Five counties have less than 25% ZIP coverage, indicating potential food access gaps in rural areas.
* Food pantries account for ~60% of providers, while meal programs and nutrition initiatives are far less common.
* 92% of providers operate from permanent locations, while only ~8% are mobile services, limiting outreach to transportation-constrained communities.
* Most organizations operate weekday-only schedules, which may create access barriers for working households.
* 23% of records required follow-up due to incomplete or inconsistent data, highlighting ongoing data quality challenges.

By transforming fragmented food security data into a structured dataset and interactive analytics platform, the project enables community organizations, policymakers, and nonprofits to:

* Identify geographic food access gaps
* Evaluate service availability across counties and ZIP codes
* Understand eligibility restrictions and operational barriers
* Support data-driven planning for food assistance programs

If you'd like to explore the analysis interactively, you can view the dashboard here:  
[Hoosier Uplands Data Library – Food Security Sector](https://public.tableau.com/views/FoodSecurity_17648911338840/FoodSecurity?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link). The dashboard was designed with accessibility in mind, including the use of a color-blind friendly palette to ensure that patterns and comparisons remain clear for all users.

<i>Technology Stack: Python, BeautifulSoup, Selenium, Pandas, BigQuery, Google Maps API, Tableau</i>
