# OM 620 - Assignments Overview

This repository showcases the work I accomplished for the **Tools and Technologies for Business Analytics** course (OM 620).

For these assignments I was asked to clean the data and calculate safety stock levels for the SKUs matching the finished goods and designated as make-to-stock. 

According to the Association for Supply Chain Management, **safety stock** is *"inventory that is carried to protect against forecast errors, as well as fluctuations in demand"*. It prevents stockouts and provides better customer service. 

## Assignments Summary 

### Assignment 1 - Data Cleaning 

- **Dataframe formatting** to standardize the column names 

- **Data inspection using the `describe` function** to identify and correct the oddities/anomalies, such as negative values for `unit_price` and `order_quantity` 

- **Identify the missing values (NaN)** and drop them in the rows where the `sku_number` is missing 

- **Filter** the dataset to focus on finished goods that are make-to-stock

### Assignment 2 - Safety Stock Calculation 

- **Group** by `sku_number` and **aggregate** with `quantity_order` (minimum, maximum, average, median, variance, and standard deviation), and `lead_time` (average)

- **Calculate safety stock** using the formula: **Z×σ×√L**​ 

where: 
- Z the service level coefficient (using `scipy.stats.norm.ppf`)
- σ the demand's standard deviation
- L the lead time

- Computation for three different service level coefficients: 75%, 90%, and 95%

- Focus on the 95% service level to **analyze the distribution** of safety stock values

## Findings/Accomplishments 

To clean the data, I formatted the column names to have a standardized convention. I dropped the NaN values in `sku_number` because they are not necessary to compute safety stock. Additionally, the number of `NaN` values was not representative. I also changed the negative values in the `order_quantity` and `init_price` columns to their absolute values. 

The inspection of the dataset showed a higly consistent `lead_time`, a price stability in `unit_price` and a constant distribution of `order_quantity` centered around 80 units. 

The safety stock calculations show that when increasing the service level from 75% to 95%, there is a significant increase in the safety stock for some SKUs. 

I also noticed that, based on the 95% service level, some SKUs have much lower or higher safety stock than their average order quantity. 