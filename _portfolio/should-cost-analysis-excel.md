---
title: "Should-Cost Analysis - Excel"
excerpt: "Developing a should-cost model for a CNC-machined titanium bracket to identify cost drivers and evaluate cost-reduction opportunities."
collection: portfolio
permalink: /portfolio/should-cost-analysis-excel/
---

## Project Overview

As part of the "Strategic Total Cost Management" class, this group project applied **should-cost modeling and strategic cost management** to an CNC-machine **Ti-6AI-4V Grade 5 titanium bracket** used in an aerospace/defense application. The analysis evaluated the underlying material, machining, overhead, administrative, and profit components contributing to the supplier's price. Using **Excel**, a detailed cost model was developed to identify the primary cost drivers and evaluate opportunities to reduce manufacturing costs while maintaining aerospace-grade requirements. 

## Business Problem

The supplier's initial quote was **$265 per unit**, with material and labor cost increases cited as justification for the price. The component also had a high **10:1 buy-to-fly (BTF) ratio**, meaning a significant amount of titanium was required relative to the finished weight of the bracket. 

The objective was to identify the factors driving the cost of the component and evaluate potential strategies to reduce the cost that could improve material utilization and manufacturing efficiency. 

## Should-Cost Model

### Industry Cost Profile
First, the **industry cost profile** was developed to establish a benchmark for how the total price could be distributed across the cost elements. The profile decomposed the price into **direct materials, direct labor, manufacturing overhead, G&A, and profit** based on industry cost structure data retrieved on **Anklesaria's website**. 

This benchmark provided a reference point for evaluating the supplier's cost model and identifying areas that differed from industry expectations. The comparison showed differences in areas such as overhead and G&A, while labor was more aligned with the industry profile. 

![Industry Cost Profile]({{site.baseurl}}/images/industry-cost-profile.png)

### Cost Inputs and Assumptions
The cost model included product, material, and machining assumptions to estimate the underlying cost of producing the bracket. The finished component weighed **7.5oz (0.2126kg)** and used Ti-6AI-4V Grade 5 titanium priced at **$50/kg**. 

The baseline material calculation assumed a  **10:1 BTF ratio** and a **3% scrap factor**. Machining assumptions included setup time, batch size, cycle time, labor rate, and machine rate. Additional manufacturing overhead, G&A, and profit were also included to develop the supplier price. 

![Assumptions and Inputs]({{site.baseurl}}/images/assumptions-inputs.png)

### Inventory and Order Policy
An inventory decision model was developed to determine **order quantities, ordering frequency, and annual inventory-related costs** based on demand, ordering and holding costs. 

The analysis also showed the effect of **aggregating orders across multiple products**. The resulting shipment quantity was compared with available truck capacity, and the ordering policy was adjusted when the calculated quantity exceeded the 1,800-unit transportation capacity. 

![Inventory Aggregation]({{site.baseurl}}/images/excel-inventory-aggregation.png)

### Cost Driver Analysis
**Material utilization and machining** were identified as the major opportunities for cost improvement. The key cost drivers included the buy-to-fly ratio, finished bracket weight, titanium price, machine time, cycle time, and labor and machine rates. The baseline 10:1 BTF ratio was important because it represented the amount of raw titanium required relative to the finished component.  

![Cost Drivers Table]({{site.baseurl}}/images/key-cost-drivers.png)

### Baseline vs. Optimized Should-Cost Model
The baseline model produced a modeled supplier price of **$278.06/unit**, including direct material, machining labor, manufacturing overhead, G&A, and profit. 

An optimized scenario reduced the BTF ratio from **10:1 to 1.8:1**, decreasing modeled direct material cost from **$109.50 to $19.14/unit**. Under the model's assumptions, the resulting modeled supplier price decreased to **$165.82/unit**. This represented a reduction of **$112.24/unit** or around **40%** compared with the $278.06 baseline price. At an annual volume of 10,000 units, the model identified a potential cost-reduction opportunity. 

![Material Cost Build-Up and Sould-Cost Models]({{site.baseurl}}/images/baseline-and-optimized.png)  

## Cost Reduction Opportunities

Based on the identified cost drivers, several cost-reduction strategies were evaluated. These included improving material utilization through **optimizing CNC machining processes, negotiating long-term titanium supply agreements, improving CNC programming, and redesigning the bracket to reduce material usage and weight**. **CNC process optimization and BTF reduction** were identified as high-impact opportunities. The evaluation also considered potential risks and implementation requirements, including aerospace sertification, structural performance, production disruption, and required process investments. 

## Key Findings

The should-cost analysis highlighted important insights: 
1. **Industry cost profiles provide a useful benchmark for price analysis**: decomposing the total price into expected material, labor, overhead, G&A, and profit components helped identify areas of the cost structure that needed more investigation.
2. **Material utilization was a major cost-reduction opportunity**: the high baseline BTF ratio increased titanium requirements, making yield improvement an important driver of the cost.
3. **Cost decomposition provided greater visibility than evaluating the supplier price alone**: breaking the price into cost elements made it possible to understand which assumptions and cost drivers had the greatest impact in the final price. 
4. **Cost-reduction opportunities need also to be evaluated operationally**: strategies such as material reduction and machining optimization offered potential savings but involved quality, certification, investment, and production considerations. 

This project demonstrated how industry benchmarking and should-cost models can be combined to evaluate supplier cost structures, identify key cost drivers, and support sourcing and cost-reduction decisions.