---
title: "KM_model.rmd"
author: "Xinyi Shang"
date: "2024-12-04"
output: 
  pdf_document:
    keep_md: true
---




### Declaration

**Status:** *C (censored), CL (censored due to liver transplant), or D (death)*

For survival analysis:

- Status `C` and `CL` are classified as **censored** (`event = 0`).
- Status `D` is classified as **death** (`event = 1`).




## Overall Survival Result

![](KM_model_files/figure-latex/unnamed-chunk-2-1.pdf)<!-- --> 

\newpage





Table: Kaplan-Meier Survival Summary by Yearly Intervals

|Time Interval (Years) | At Risk| Events| Censored| Survival Probability| Lower CI| Upper CI|
|:---------------------|-------:|------:|--------:|--------------------:|--------:|--------:|
|[0, 1)                |     276|     19|        0|                 0.93|     0.90|     0.96|
|[1, 2)                |     257|     10|        1|                 0.89|     0.86|     0.93|
|[2, 3)                |     246|     22|       12|                 0.81|     0.77|     0.86|
|[3, 4)                |     212|     14|       29|                 0.76|     0.71|     0.81|
|[4, 5)                |     169|      9|       24|                 0.71|     0.66|     0.77|
|[5, 6)                |     136|      6|       18|                 0.68|     0.62|     0.74|
|[6, 7)                |     112|      9|       23|                 0.62|     0.55|     0.69|
|[7, 8)                |      80|      6|       15|                 0.57|     0.50|     0.64|
|[8, 9)                |      59|      5|       13|                 0.51|     0.43|     0.60|
|[9, 10)               |      41|      6|        8|                 0.42|     0.34|     0.53|
|[10, 11)              |      27|      3|        7|                 0.37|     0.28|     0.48|
|[11, 12)              |      17|      2|       10|                 0.31|     0.21|     0.45|

\newpage

## Survival Result by Drug

![](KM_model_files/figure-latex/unnamed-chunk-5-1.pdf)<!-- --> 


Table: Log-Rank Test Results for Drug Groups

| Chi-Squared Statistic| Degrees of Freedom| P-Value|
|---------------------:|------------------:|-------:|
|                0.4049|                  1|  0.5246|

**Interpretation:** 

The p-value is 0.5246, which is significantly higher than the threshold of 0.05. This indicates no statistically significant difference in survival between the drug groups. Therefore, the results suggest that D-penicillamine does not demonstrate a statistically significant difference from the placebo group.

\newpage

## Survival Result by Other Covariates

### Edema

![](KM_model_files/figure-latex/unnamed-chunk-7-1.pdf)<!-- --> 


Table: Log-Rank Test Results for Edema Groups

| Chi-Squared Statistic| Degrees of Freedom|P-Value |
|---------------------:|------------------:|:-------|
|               53.0933|                  1|<0.0001 |


The log-rank test for edema groups reveals a Chi-Squared statistic of 53.0933 with 1 degree of freedom and a highly significant p-value (<0.0001), indicating a statistically significant difference in survival curves between the groups. This result suggests that presence of edema plays a critical role in influencing survival outcomes, with distinct survival probabilities observed across the groups.

\newpage

### Stage

*histologic stage of disease (1, 2, 3, or 4)*

![](KM_model_files/figure-latex/unnamed-chunk-9-1.pdf)<!-- --> 


Table: Log-Rank Test Results for Stage Groups

| Chi-Squared Statistic| Degrees of Freedom|P-Value |
|---------------------:|------------------:|:-------|
|               44.6499|                  3|<0.0001 |

The log-rank test for stage groups shows a Chi-Squared statistic of 44.6499 with 3 degree of freedom and a highly significant p-value (<0.0001). These results strongly indicate that there is a statistically significant difference in survival curves between the stage groups. This suggests that the stage of the disease has a significant impact on survival outcomes. 

