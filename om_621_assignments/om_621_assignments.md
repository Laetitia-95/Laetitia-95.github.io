# Advanced Visual Analytics - Transportation Cost Estimation and Forecasting

## Project Overview

As part of the *Advanced Visual Analytics* class (OM 621), I was assigned a project focusing on the analysis and visualizations of the transportation cost estimation and forecast. This project explores how a company can better allocate transportation budget and cost across departments and modes, despite invoice delays, using historial data. 

The repository includes: 
* **3-minute story** to describe the company's problem and solution
* **Storyboard** to visualize the steps from the issue to the recommendations
* **Python** for analysis and visualizations between delay and transportation modes 
* **Power BI** for more detailed analysis and forecast 

The project aims to provide solutions that support a company's strategic decision-making related to allocating costs for different modes of transportation. 

Find the video presentation: [here](project_presentation.mp4)

## Assignments Overview

### Assignment 1 - Situation Overview

* **Identify the audience** involved in the situation from executive level, to manager level, to operational team, define what I want the audience to understand and replicate, and how I am going to do it 

* **Identify and gather the data** needed to proceed to the exploration and visualizations

* **Understand the problem and what solution is best suited**: the company experiences delay between invoice dates and shipment dates making it complicated for the accounting department to estimate and allocate transportation budgets across the departments. Each departments use different carriers and transportation modes adding complexity to the situation. Historical data shows that each carrier is most cost-efficient with a specific transportation mode. The implementation of a forecasting model and transportation cost estimation is best suited to accordingly allocate cost by transportation mode. 

The following picture summarizes the situation in a storyboard format: [alt text](image.png) 

### Assignment 2 - Delay Analysis & Visualization using Python

* **Calculate average, minimum and maximum** invoice amounts

* **Create basic visualizations**: 
    * Faceted bar charts to display the number of transportation by manufacturing sites and region

    * Bar chart to display how many times each mode were used

    * Histograms graph to display delay across sites and regions

    * Scarter plots to find relationships between delay and invoice amount, invoice amount across regions, and invoice amount across sites

    * Density graph to show the relationship between delay and transportation mode 

### Assignment 3 - Delay Distribution & Invoice Time Series using Python

* **Deeper delay distribution analysis** across modes using a boxplot graph

* **Analyze patterns/seasonality** in invoicing timing per modes using faceted line graph 

* **Discuss** the findings and patterns 

### Assignment 4 - Transportation Cost Estimation and Forecasting using Power BI

* **Develop interactive dashboards** focusing on transportation costs across modes, and forecasting

* **Add filters**, such as years, sites, divisions, for deeper analysis

* **Generate a one-year projection** of transportation costs per mode to support future budget allocation

## Findings/Accomplishments 

* No relationship was found between delay and sites, regions and invoice amounts 

* The density graph shows a relation between delay and mode

* Across the years, total invoice amount grows consistently from January to November and drops in December. Every year total invoice amount increase, and these patterns do not differ by transportation mode 

* Major difference in trending invoice costs: container ship modes appear to be increasing in cost over time, whereas parcel invoices remain relatively stable.

* Container modes appear to be the ones experiencing greater delay compared to parcel modes 