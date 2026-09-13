---
title: "Transportation Cost Analysis - Python"
excerpt: "Analyzing transportation costs dataset using Python to identify correlations, patterns, and trends to support transportation cost estimation and forecasting."
collection: portfolio
permalink: /portfolio/transportation-cost-analysis-python/
---

## Project Overview

As part of the "Advanced Visual Analytics" class, I was assigned a project on identifying correlations, patterns, and trends to support transportation cost estimation and forecasting. Using Python, I cleaned, explored, and prepared the dataset for analysis, and investigated relationships between delays, invoice amounts, manufacturing sites, regions, and transportation modes. I also created visualizations to better understand delay patterns and changes in invoice amounts over time.
This project explores how a company can better allocate transportation budget and cost across departments and modes, despite invoice delays, using historial data.

## Business Problem

Transportation is an important part of supply chain operations because transportation costs can vary depending on multiple factors such as transportation mode, location, and delivery timing. In this project, the objective was to analyze historical transportation data and identify patterns that could support transportation costs understanding and estimation. 
The analysis focused on understanding the distribution of delays across regions and sites, determining factors associated with the delay between shipping date and invoice date, and identifying patterns in transportation costs over time. 

## Data

The dataset used was *tr_data_22_24.csv* and included the following columns: `site`, `mode`, `division`, `region`, `destination`, `shipping_date`, `invoice_date` and `usda_invoice_amount`. It contained 208799 rows with some null values for `site`, `mode`, and `division`. Therefore some data cleaning was needed, which included: 

- Dealing with null values
- Excluding unnecessary transportation mode ('other')
- Data frame formatting
- Renaming transportation modes

![Python data cleaning code]({{site.baseurl}}/images/transportation-data-cleaning-code.png)

## Data Exploration 

During the exploration phase, I investigated transportation activity and delays to better understand how the data varied across regions, manufacturing sites, and transportation modes.

### Transportation Activity
In the exploration part of the project, I answered the following questions: 
1. Which manufacturing site has placed the largest number of transportation tasks by region?
![Shipments by site and region]({{site.baseurl}}/images/transportation-region-site-code-graph.png)

2. Which transportation mode has been utilized the most?
![Shipments by mode code]({{site.baseurl}}/images/shipments-by-mode-code.png)
![Shipments by mode graph]({{site.baseurl}}/images/shipments-by-mode-graph.png)

### Delay Analysis
I created a `delay` feature based on the difference between the shipping date and invoice date.
![Delay Feature Code]({{site.baseurl}}/images/code-delay-feature.png)

Once this delay feature created, I analyzed different relationships possible: 
- Delay distribution across regions
![Delay Across Regions]({{site.baseurl}}/images/delay-regions.png)
- Delay distribution across manufacturing sites
![Delay Across Sites]({{site.baseurl}}/images/delay-sites.png)
- Delay distribution across transportation modes
![Delay Across Modes]({{site.baseurl}}/images/delay-modes.png)

The analysis showed that delay between the shipment dates and the invoice date varied across the mode of transportation. To examine these differences more closely, I created a boxplot showing the distribution of delays for each mode. Less-than Container Load experienced the largest delay, while Less-than Truckload was the most utilized transportation mode. The parcel modes generally experienced the smallest delays.

![Delay Distribution Across Modes]({{site.baseurl}}/images/delay-modes-boxplot.png)

## Transportation Cost Patterns & Trends

In order to identify any patterns and trend in the transportation cost, I created a line chart representing the total invoice amount by month and mode of transportation. 

![Total Invoice Amount per Month per Mode]({{site.baseurl}}/images/transportation-patterns.png)

## Key Findings

The analysis showed several patterns in transportation costs: 
1. **Seasonal pattern**: The total invoice amount for 2022, 2023, and 2024 follow a consistent time-series pattern. For each year, the total invoice amount grows consistently from January to November and drops in December. 
2. **Year-over-year growth**: The total invoice amount increase from 2022 to 2024, indicating an overall upward trend in transportation costs. 
3. **Differences by transportation mode**: `less_container_load` and `full_container_load` had the highest total invoice amounts and showed higher delay distributions compared with other transportation modes. 
4. **Different cost trends by mode**: The trends in invoice costs varied by transportation mode. Container shipping modes showed increasing invoice amounts over time, while parcel invoices remained relatively stable.

These findings indicate that transportation mode and seasonality should be considered when estimating and forecasting transportation costs. The consistent patterns observed from 2022 to 2024 could provide useful information to plan and allocate the transportation budget in advance. The increase in invoice amounts also suggests that transportation costs may increase in 2025.  