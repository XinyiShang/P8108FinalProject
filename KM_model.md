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


Table: Kaplan-Meier Survival Summary by Year

|Time Group (Years) | At Risk| Events| Censored| Survival Probability| Lower CI| Upper CI|
|:------------------|-------:|------:|--------:|--------------------:|--------:|--------:|
|0.00-1.00          |     389|     30|        0|                 0.93|     0.90|     0.95|
|1.00-2.00          |     366|     20|        3|                 0.88|     0.85|     0.91|
|2.00-2.98          |     317|     31|       18|                 0.80|     0.77|     0.84|
|2.99-4.00          |     249|     19|       49|                 0.75|     0.71|     0.80|
|4.00-4.98          |     200|     15|       34|                 0.70|     0.66|     0.75|
|4.99-6.00          |     167|     10|       23|                 0.66|     0.62|     0.72|
|6.00-6.98          |     117|     11|       39|                 0.61|     0.56|     0.67|
|6.99-8.00          |      85|      7|       25|                 0.57|     0.51|     0.63|
|8.00-8.98          |      57|      6|       22|                 0.52|     0.45|     0.59|
|8.99-10.00         |      37|      7|       13|                 0.44|     0.37|     0.53|
|10.00-10.98        |      28|      3|        6|                 0.40|     0.32|     0.49|
|NA                 |      15|      2|       11|                 0.35|     0.27|     0.46|

\newpage

## Survival Result by Drug

![](KM_model_files/figure-latex/unnamed-chunk-4-1.pdf)<!-- --> 


Table: Log-Rank Test Results for Drug Groups

| Chi-Squared Statistic| Degrees of Freedom| P-Value|
|---------------------:|------------------:|-------:|
|                0.1017|                  1|  0.7498|

**Interpretation:** 

The p-value is 0.7498, which is significantly higher than the threshold of 0.05. This indicates no statistically significant difference in survival between the drug groups. Therefore, the results suggest that D-penicillamine does not demonstrate a statistically significant difference from the placebo group.

\newpage

## Survival Result by Other Covariates

### Edema

![](KM_model_files/figure-latex/unnamed-chunk-6-1.pdf)<!-- --> 


Table: Log-Rank Test Results for Edema Groups

| Chi-Squared Statistic| Degrees of Freedom|P-Value |
|---------------------:|------------------:|:-------|
|                62.332|                  1|<0.0001 |


The log-rank test for edema groups reveals a Chi-Squared statistic of 62.332 with 1 degree of freedom and a highly significant p-value (<0.0001), indicating a statistically significant difference in survival curves between the groups. This result suggests that presence of edema plays a critical role in influencing survival outcomes, with distinct survival probabilities observed across the groups.

\newpage

### Stage

*histologic stage of disease (1, 2, 3, or 4)*

![](KM_model_files/figure-latex/unnamed-chunk-8-1.pdf)<!-- --> 


Table: Log-Rank Test Results for Stage Groups

| Chi-Squared Statistic| Degrees of Freedom|P-Value |
|---------------------:|------------------:|:-------|
|               70.0762|                  1|<0.0001 |

The log-rank test for stage groups shows a Chi-Squared statistic of 70.0762 with 1 degree of freedom and a highly significant p-value (<0.0001). These results strongly indicate that there is a statistically significant difference in survival curves between the stage groups. This suggests that the stage of the disease has a significant impact on survival outcomes. 

