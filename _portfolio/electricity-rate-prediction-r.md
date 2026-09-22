---
title: "Consumer Electricity Rate Prediction - R"
excerpt: "Predicting residential electricity rates and classify ZIP codes into pricing tiers using R, feature engineering, data visualization, regression, and classification models."
collection: portfolio
permalink: /portfolio/electricity-rate-prediction-r/
---

## Project Overview

This group project focused on analyzing residential electricity rates across the United States in 2024 using **R**. The project aimed to predict residential electricity rates and classify ZIP codes into high and low pricing tiers. 

The analysis included data preparation, feature engineering, exploratory data analysis, regression and classification modeling. Multiple models were developed and evaluated to compare predictive performance and to identify important factors associated with residential electricity rates. 

## Business Problem

Electricity rates vary widely across the U.S. based on factors such as region, climate, and utility structure. These differences make it difficult for households, utilities, and regulators to understand cost drivers and how rates may vary across location. 

This project aimed to use historical electricity rate data to develop predictive models for **residential electricity rates** and compare their performance and interpretability, to identify the strongest predictors of residential electricity rates and rate tiers, and to provide actionable insights for stakeholders. 

## Data

The dataset was obtained from *Data.gov* and was *iou_zipcodes_2024.csv* It contained 49,004 observations and 9 original features including `zip`, `eiaid`, `utility_name`, `state`, `service_type`, `ownership`, `rest_rate` and `comm_rate` and `ind_rate`. 

### Data Cleansing and Preparation
Before any exploratory analysis, the dataset was inspected and prepared. No missing values, duplicate rows, or invalid extreme outliers were found. 

For the classification analysis, outliers in commercial and industrial electricity rates were handled using z-score standardisation. Selected categorical variables were also converted to factors to prepare the data for modeling. 

## Feature Engineering 

Several features were created to capture additional relationships in the data and support the exploratory analysis and predictive models. 

### Rate-Based Features
- `ind_minus_res` -  industrial vs. residential price differences
- `comm_minus_res` - commercial vs. residential price differences
- `comm_res_ratio`  - normalizes commercial rates relative to residential
- `rate_spread` -  overall variability across customer classes

### Geographic Features
- `zip3` - captures localized regional pricing patterns
- `climate_zone` - incorporates environmental and geographic differences
- `state_res_rate` - aligns ZIP‑level pricing with statewide averages

### Utility-Level Features
- `zip_count_by_utility` - reflects service area size and utility structure

### Transformations
- `log_res_rate` - used during EDA to assess skewness and distribution shape

### Target Variable (Classification)
- `rate_tier` - categorical grouping of residential rates for classification

![Code 1 Feature Engineering]({{site.baseurl}}/images/feature-engineering-code1.png)
![Code 2 Feature Engineering]({{site.baseurl}}/images/feature-engineering-code2.png)
![Code 3 Feature Engineering]({{site.baseurl}}/images/feature-engineering-code3.png)

## Exploratory Data & Visualization

The exploratory data analysis examined the distribution of electricity rates and identify patterns across climate zones, and geographic locations. 

### Electricity Rate Distributions
Residential, commercial, and industrial rates were concentrated between **$0.10 and $0.20 per kWh**, while industrial rates showed a lower cluster around **$0.05 -$0.12 per kWh**. All three distributions were slightly right-skewed. 

![Residential Rate Distribution]({{site.baseurl}}/images/residential-rate-histogram.png)
![Commercial Rate Distribution]({{site.baseurl}}/images/commercial-rate-histogram.png)
![Industrial Rate Distribution]({{site.baseurl}}/images/industrial-rate-histogram.png)

### Residential Rate by Climate Zone
Residential electricity rate was also compared by climate zones. The **marine climate zone** showed the widest variability, while hot-humid and mixed-humid zones showed lower and more tightly clustered rates. 

![Residential Rate by Climate Zones]({{site.baseurl}}/images/residential-climate-zone.png)

### Correlation & Geographic Patterns
The correlation analysis (heat map) showed strong relationships among residential, commercial, and industrial electricity rates. 

![Correlation Heatmap]({{site.baseurl}}/images/heatmap-numeric-features.png)

Geographic analysis also showed differences across the United States, with higher residential rates concentrated in the **West Coast and Northeast**, while Central and Mountain states showed lower average rates. 

![Residential Rate US Map]({{site.baseurl}}/images/residential-us-map.png)

## Regression Modeling

Two regression approaches were developed to predict residential electricity rates: **Multiple Linear Regression** and **Regression Tree**. The data was divided into 70% training and 30% testing sets to evaluate model performance on unseen data. 

### Multiple Linear Regression (MLR)
Multiple model specifications were tested using different combinations of features. Models were evaluated using **RMSE, R², and residual diagnostics**, with meaningful predictors based on  practical understanding of the variables and insights from EDA. 

The final model was selected based on the lowest test RMSE and strongest generalization. Key predictors included commercial rate, industrial rate, service type, and the number of ZIP codes served by each utility. 

![Fifth Model Attempt Code]({{site.baseurl}}/images/mlr-code.png)
![Regression RMSE]({{site.baseurl}}/images/regression-rmse.png)

#### Model Interpretation 
The selected model showed that commercial electricity rates had a strong relationship with residential rates. A **$0.01 increase in commercial rate is associated with a $0.0063 increase in residential rate**. Industrial rates also showed a positive relationship with residential rates with a $0.01 increase in industrial rate corresponding to a $0.00001 cent increase in residential rate. Delivery utilities were associated with residential rates approximately $0.0417 lower on average. 

### Regression Tree
A regression tree was also developed to predict residential electricity rates. The initial tree was fully gorown using the available predictors. Cross-validated erros was used to identify the pruning parameter that minimized RMSE and reduce unnecessary splits. 

The final regression tree identified **commercial rate, ZIP code prefix (zip3) and service type delivery** as important predictors, and **industrial rate** as a minor contributor. Commercial rate and ZIP3 created the main splits in the three, while service type delivery was associated with lower reqsidential electricity rate branches. 

![Pruned Regression Tree]({{site.baseurl}}/images/regression-tree-pruned.png)

### Regression Model Comparison
The **MLR model achieved the lowest test RMSE** and provided the strongest predictive accuracy and generalization. The regression tree had higher error and more variability across splits but provided an interpretable view of how electricity rates were segmented across key predictors. 

## Classification Modeling

Two classification approaches were developed to classify residential electricity rates into **high and low pricing tiers**: **Logistic Regression** and **Classification Tree**. The data was divided into 70% training and 30% testing sets and the variables derived from residential rates were removed from the modeling data to prevent data leakage.

### Logistic Regression 
Multiple logistic regression models were tested to reduce multicollinearity and identify statistically significant predictors. The final model was evaluated using a **confusion matrix** on both the training and validation sets. 

On the validation set, the model achieved **91.5% accuracy**, with **90% sensitivity**, **92.95% specificity**, and **92.69% precision**. Key predictors were **commercial rate, industrial rate, climate zone, service type and the ZIP count by utility**, with commercial rate identified as the most impactful predictor. 

![Third Model Attempt Code]({{site.baseurl}}/images/logistic-regression-code.png)
![Logistics Regression Result]({{site.baseurl}}/images/logistics-code-results.png)
![Confusion Matrix Validation Set]({{site.baseurl}}/images/confusion-matrix.png)

### Classification Tree
A classification tree was developed to classify residential electricity rates into high and low pricing tiers. The fully grown tree was evaluated using the **complexity parameter (CP) table** and confusion matrices for the training and validation sets. The main predictors identified were **commercial rate, industrial rate, and climate zone**. 

![Classification Tree]({{site.baseurl}}/images/classification-tree.png)

### Classification Model Comparison
The **classification tree** achieved approximately **99% accuracy** and outperformed the logistic regression model across the main classification metrics. The tree was effective at capturing non-linear relationships and provided clear segmentation of the factors associated with high and low residential electricity rate tiers. 

The logistic regression model still achieved strong predictive performance and provided a more stable statistical framework for understanding the relationships between predictors and rate tiers. 

## Key Findings

Across both regression and classification models, the analysis provided several key insights into residential electricity rates and predictive modeling: 
1. **Commercial and industrial rates were important predictors of residential electricity rates**
2. **Geographic characteristics were important for prediction**: `ZIP3` contributed to the regression models, while `climate_zone` contributed to the classification models. 
3. **Multiple Linear Regression provided the strongest regression performance** with the lowest RMSE. 
4. **Classification tree achieved the strongest classification performance** and captured non-linear relationships in the data. 

The project demonstrated how regression and classification models can be combined to predict residential electricity rates, identify important pricing patterns, and provide interpretable insights from electricity rate data. 