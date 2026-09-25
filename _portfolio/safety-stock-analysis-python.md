---
title: "Safety Stock Analysis - Python"
excerpt: "Analyzing safety stock requirements across different service levels using Python."
collection: portfolio
permalink: /portfolio/safety-stock-analysis-python/
---

## Project Overview

As part of the "Tool and Technologies for Analytics" class, I was assigned a project on calculating **inventory safety stock** for finished goods managed under a make-to-stock (MST) stategy, using **Python**. The analysis focused on understanding how different target service levels affect the amount of safety stock required across individual SKUs. The project combined data preparation, SKU-level demand and lead-time analysis, and safety stock calculations at **75%, 90%, and 95% service levels** to evaluate the relationship between inventory requirements and product availability. 

## Business Problem

Companies operating a MST strategy need to maintain enough inventory to meet customer demand while avoiding unnecessary inventory costs. Because demand can vary, safety stock provides additional inventory to reduce the risk of stockouts. The challenge is determining an appropriate level of safety stock for each SKU. Higher level improve product availability but also require more inventory. This analysis evaluates safety stock requirements at different service levels to show this tradeoff and support inventory planning decisions. 

## Data

The dataset used was *df*. It contained 400233 rows and included 9 variables: `sku_number`, `inventory_type`, `stocking_type`, `lead_time`, `unit_price`, `manufacturing_site`, `division_code`, `transaction_date`, and `order_quantity`. 

### Data Cleaning and Transformation

The dataset was check for missing values, inconsistent columns names, and unusual values. Column names were standardized to create a consistent format, and missing SKU identifiers were taking care of because the SKU was the primary unit of analysis.

For the safety stock analysis, the data was filtered to include **finished goods(FG)** managed under a **make-to-stock (MTS)** strategy and transactions with non-negative order quantities. The remaining transactions were grouped by SKU. For each SKU, order quantity was summarized using the **minimum, maximum, mean, median, variance, and standard deviation**, and lead time was aggregated using its **average value**. 

![Safety Stock cleaning code 1]({{site.baseurl}}/images/safety-stock-cleaning-code1.png)

![Safety Stock cleaning code 2]({{site.baseurl}}/images/safety-stock-cleaning-code2.png)

## Safety Stock Analysis

### Service Level and Safety Stock Calculation
Safety stock was calculated for three target service level: **75%, 90% and 95%**. Eacg service level was converted into its corresponding **z-score**, representing the level of protection against demand variability. Safety stock for each SKU was calculated using the following formula: **Safety Stock = Z * Standard Deviation of Demand * √Average Lead Time (Z×σ×√L​)**. 

Calculating safety stock at multiple service levels helped compare how increasing the desired level of product availability affects inventory requirements. 

![Z-score Calculation]({{site.baseurl}}/images/z-score-calculation.png)

![Safety Stock 75%]({{site.baseurl}}/images/75-safety-stock.png)
![Safety Stock 90%]({{site.baseurl}}/images/90-safety-stock.png)
![Safety Stock 95%]({{site.baseurl}}/images/95-safety-stock.png)

![Safety Stock Final Table]({{site.baseurl}}/images/safety-stock-final-table.png)

### Safety Stock Results
The analysis showed that safety stock requirements increased as the target service level increased from 75%, 90%, and 95%. SKUs with greater variability in order quantities required more safety stock, while SKUs with more stable demand required less safety stock. 

## Key Findings

The safety stock analysis showed important inventory management insights: 
1. **Higher service levels require more safety stock**: increasing the service level from 75% to 90% and 95% increased the amount of inventory required to protect against demand variability.  
2. **Safety stock requirements vary by SKU**: products with greater variability in order quantity required higher sfety stock levels.
3. **Lead time influences inventory requirements**: longer replenishment lead times increase the period over which demand uncertainty must be covered, contributing to higher safety stock requirements. 
4. **Service level decisions involve an inventory trade-off**: higher service levels provide greater protection against stockouts, but they increase the amount of inventory that must be maintained, therefore the cost of holding inventory. 
 