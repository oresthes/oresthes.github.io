---
layout: post
title:  "Generalized Linear Models"
date:   2017-12-25 13:07:53 -0600
categories: jekyll update
---


This notebook discusses the theory behind the Generalized Linear Model.  
This is an an extraction of material and examples from various sources I have come across and found useful over time.

Sources:  

1. *Faraway* - Extending the Linear Model with R
2. *Nelder, McCullagh* - Generalized Linear Models 



# Preamble 

Before discussing GLM, a brief overview of the processes associated with model fitting.  

## Model Selection 

Models must be selected from a particular class, which has to be relevant to the kind of data under study. Assumptions involved regarding the data that is used with GLM are listed below:  

- Independent or at least uncorrelated observations. This excludes time series and spatial processes data, which exhibit autocorrelation.  
- A single error term is allowed in the error structure.  

Regarding the choice of scale for analysis, we might need to keep in mind certain characteristics (by scale, we can consider using original scale (Y) or modified, (log(Y) or sqrt(Y) etc.). For **classical linear regression**, a good scale should contain:  

- Constancy of Variance  
- Approximate Normality of Errors
- Additivity of systematic effects  

This scale need not exist, also different scales might satisfy the different conditions above.  

GLMs reduces greatly scaling problems.  
- Constancy of Variance and Normality are **not required**  
- Dependence of Variance on the mean must be known 
- Additivity of effects is required. It can be specified to hold on a transformed scale.  

On the other hand, we have to deal with the choice of covariates, x-variables, to be included in the systematic part of the model.  In general out of p covariates, we are required to find a subset of these that is in some sense best for constructing the fitted values **$\hat\mu$**:  

$$
\hat\mu_i = \sum_j x_{ij}\hat\beta_{j}
$$

