---
title: "Voice of the Customer and Decision Analysis - Excel"
excerpt: "Using Voice of the Customer analysis and an Excel decision model to identify smartphone improvement priorities and evaluate battery life improvement."
collection: portfolio
permalink: /portfolio/voc-decision-analysis/
---

## Project Overview

As part of the "Quality Management" class, this project applied **Voice of Customer (VOC) analysis and decision modeling** to evaluate smartphone quality attributes and identify opportunities for product improvement.  

A customer survey was created and used to measure the importance and perceived performance of seven smartphone quality attributes. The results were analyzed using a **performance-importance matrix** to identify improvement priorities. Battery life was selected for further analysis using an influence diagram, an Excel decision model, and two-way sensitivity analysis to evaluate how different levels of battery improvement could affect customer satisfaction, added value, cost, and profit. 

## Voice of the Customer Analysis

A **survey contening 20 questions** was completed by six respondents and included questions related to customer characteristics, attribute importance, satisfaction, likelihood of recommendation, overall satisfaction, and open-ended improvement suggestions. 

Seven quality attributes were evaluated: **intuitive interface, reliability, AI features, battery longevity, security, value for money, and performance**. the average performance and importance scores for each attribute were calculated in Excel and plotted on a **performance-importance matrix**. This allowed the attributes to be separated according to whether they represented strengths, improvement priorities, or areas requiring less immediate attention. 

![Performance-Importance Matrix]({{site.baseurl}}/images/performance-importance-matrix.png)

## Customer Priorities

The VOC analysis identified **battery longevity and security** in the *Concentrate Here* quandrant, indicating relatively high importance but lower perceived performance. Reliability, performance, and value for money were positioned as strengths that only require to be maintained. Customer suggestions also supported improving battery life. Based on these results, battery longevitiy was selected for the next stage of the analysis. 

## Decision Model

An **influence diagram** was then developed to structure the battery improvement decision and identify the relationships between the decision variable, uncertainty, inputs, and outcome. 

The primary decision variable was the **percentage improvement in battery life**. The model connected battery improvement to expected customer satisfaction, actual satisfaction under uncertainty, added customer value, improvement cost, and **added profit per unit**. 

![Influence Diagram]({{site.baseurl}}/images/influence-diagram.png)

## Excel Model and Assumptions

The Excel model translated the influence diagram into quantitative relationships. Current battery satisfaction was set at **3/5**, with maximum satisfaction limited to **5/5**. The model calculated expected satisfaction based on the selected battery impovement percentage, incorporated uncertainty in actual custoler satisfaction, estimated the rsulting added customer value and improvement cost, and calculated: **Added Profit = Added Value - Added Cost**. 

Because several inputs were assumptions rather than observed values, the model was designed as a **decision-analysis exercise rather than a prediction of actual smartphone profitability**. The assumptions included the relationship between battery improvement and satisfaction, value per satisfaction point, variable improvement cost, and satisfaction uncertainty. 

## Sensitivity Analysis

A **two-way sensitivity analysis** was performed in Excel to examine how added profit per unit changed across different battery improvmeent percentages and different customer satisfaction outcomes. 

Although the model produced its highest added profit under a **5% battery improvement and +2 satisfaction-point scenario**, this result was sensitive ti changes in satisfaction and was considered unrealistic because such a small battery improvement would be unlikely to generate suwh a large increase in customer satisfaction. The analysis instead identified the **25%-35% battery improvement range** as providing more stable modeled results across satisfaction scenarios. This range also represented a more noticeable customer improvement while maintaining more operationally reasonable than more extreme improvement levels. 

![Two-Way Sensitivity Analysis]({{site.baseurl}}/images/sensitivity-analysis.png)

## Recommendation and Limitations

Based on the VOC and decision analysis, the project recommended evaluating a **25%-35% improvement in battery life** rather than selecting the scenario that produced the maximum profit. The recommendation balanced customer priorities, potential satisfaction improvement, profitability, robustness across uncertain outcomes, and operational feasibility. 

The analysis had several limitations. The VOS analysis was based on only six respondents, and several decision-model inputs were assumptions. Fixed improvement costs were not incorporated, and the satisfaction uncertainty may not represent actual customer behavior. A larger and more diverse customer sample and more reliable cost and willingness-to-pay data would therefore be needed before applying the model to a real product decision. 

## Key Findings

This project demonstrated how **customer feedback can be translated into a structured managerial decison**. The VOC analysis identified areas where customer expectations were not being fully met, while the decision model evaluated one of those priorities from customer, operational, and financial perspectives. It also demonstrated the importance of **sensitivity analysis when decisions depend on uncertain assumptions**. Rather than selecting the single scenario with the highest profit, the analysis considered the stability and realism of the outcome before developing a recommendation. 
