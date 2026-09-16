---
title: "Transportation Cost Analysis - Power BI"
excerpt: "Analyzing historical transportation data using Power BI to explore transportation costs, delays, and forecasting patterns.

You can find the video presentation and project summary on [GitHub](https://github.com/Laetitia-95/OM621_assignments/tree/main)"
collection: portfolio
permalink: /portfolio/transportation-cost-analysis-powerbi/
---

## Project Overview

This part of the project focused on the general overview, delay analysis and forecasting. Using Power BI, I cleaned and standardized the data, created relationships between the datasets, and developed a DAX calculated column to measure the delay in days between the shipping date and invoice date. 

The final Power BI report included interactive pages for analyzing transportation activity costs, investigating delays across transportation characteristics, and forecasting transportation costs by mode. The report also included filters and navigation features explore the data by year, transportation mode, division, manufacturing site, region, and city. 

## Business Problem

Transportation is an important part of supply chain operations because transportation costs can vary depending on multiple factors such as transportation mode, location, and delivery timing. Understanding historical patterns can support transportation cost planning. In this project, the objective was to use historical transportation data to better understand and forecast transportation costs and budget. 
The analysis focused on developing a broad view of transportation costs across the different modes and regions, analyzing delays across transportation modes, divisions and manufacturing sites, and forecasting transportation costs up to 12 months into the future.  

## Data 

The Power BI report used three dataset: 
1. *tr_data_22_24*: this is the same dataset as the Python part, including the following columns: `site`, `mode`, `division`, `region`, `destination`, `shipping_date`, `invoice_date` and `usda_invoice_amount`. This is the primary dataset used for the analysis. 
2. *site_data*: it gathers information about the `manufacturing sites`, including `city`, `country`, `access_to_tms`, `shipping_options`, `parcel_1st_choice`, `parcel_2nd_choice`, `measurement_units`, and `currency`.
3. *division_data*: it includes the following columns: `division_code` and `division_name`

### Data Preparation 

The datasets were prepared in the Power Query before building the report. The main preparation steps included: 
- Promoting the first row to column headers
- Changing column data types
- Replacing values where needed, especially for the NA ones
- Standardized transportation mode codes into readable category names

![Power BI data prep steps]({{site.baseurl}}/images/powerbi-data-prep.png)

## Data Model

To organize the data for analysis, I created a data model with relationships between *tr_data_22_24* and the two other datasets: 
- *site_data* was connected to *tr_data_22_24* through the `manufacturing_site`column as one to many. 
- *division_data* was connected to *tr_data_22_24* through the `division_code` column as one to many.

![Power BI 1 to many relationships]({{site.baseurl}}/images/powerbi-relations.png)

## Power BI Dashboards

The Power BI report consisted of three analytical dashboards designed to provide different views of transportation activity, delays, and cost. The last dashboard included some information about the data, terms used and definitions. 

### Overview Dashboard

The *Overview* dashboard included a visualization of **total invoice amount by transportation mode and region**, with summary views of total invoice amount and average delay by city. It was possible to select the year and city of interest to explore how transportation costs and delays varied across locations and periods. 

![Power BI Overview Dashboard]({{site.baseurl}}/images/powerbi-overview.png)

### Delay Analysis Dashboard

The *Delay Analysis* dashboard focused on understanding how shipment delays varied across transportation characteristics. The dashboard included two graphs about the **average delay in days by transportation mode** and the **distribution of shipments by delay and transportation mode** grouped into 5-day bins. It was possible to select the year, division, and manufacturing site, allowing delays to be examined from different operational perspectives. 

![Power BI Delay Analysis Dashboard]({{site.baseurl}}/images/powerbi-delay-analysis.png)

### Forecasting Dashboard

The *Forecasting by Mode* dashboard displayed **total invoice amounts by year and month, together with the forecasted values. It was possible to select the transportation mode, division or manufacturing site city to explore different cost patterns. 

The forecast showed a 12-month forecast period, a 12-point seasonal cycle, and a 95% confidence interval to represent uncertainty. 

![Power BI Forecasting Dashboard]({{site.baseurl}}/images/powerbi-forecast.png)

### Data, Terms, and Definitions Dashboard

The last dashboard was the *Data, Terms, and Definitions* where some information were displayed. 

![Power BI Information Dashboard]({{site.baseurl}}/images/powerbi-information.png)

## Key Findings

The Power BI analysis supported and complemented the Python analysis by providing a visual interpretation of the transportation data: 
- **Transportation costs variation across transportation modes and regions**
- **Transportation delays varied by mode**: container transportation showed higher delays compared with parcel transportation. 
- **Seasonal pattern**: as seen in the Python analysis, transportation costs followed a pattern with an increase throughout the year before decreasing in December. 
- **Transportation costs increased over the years**: as observed in Python, the Power BI analysis confirmed the upward trend in transportation spending over the years. These patterns helped developing a 12-month forecast and supporting future transportation budget planning. 
