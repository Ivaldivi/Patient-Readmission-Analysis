# Patient-Readmission-Analysis
# Patient Readmission Exploration
#### Author: Izzy Valdivia
##### November 2025

### Project Background: 
&nbsp;&nbsp;&nbsp;&nbsp; Patient readmission is a powerful indicator of quality of care across the healthcare industry. Readmission is when a person is admitted to the hospital within 30 days of a previous discharge because there was some aspect of their care that was not handled or their condition is worsening. Health care providers and insurers frequently track patient readmission rates from hospital systems to better understand the quality of care provided at those facilities and how that affects patient outcomes. Understanding which hospitals have high readmission rates can help policymakers and insurers launch targeted improvement programs or understand what areas may need more resources. Definitive Healthcare, an analytics company focused on reporting on healthcare metrics in the United States, reports that the average hosiptal readmission rate is ~14.7%, with a range from 10.1 to 19.1% ([Definitive Healthcare, 2025](https://www.definitivehc.com/resourcesz/healthcare-insights/average-hospital-readmission-state#:~:text=What%20is%20the%20average%20hospital,to%2019.1%25%20in%20the%20U.S.)).  
&nbsp;&nbsp;&nbsp;&nbsp; With this context in mind, I am interested in creating a model to predict hospital readmission rates based on quality of care metrics for the Medicare population. I hope to understand what facets of quality of care most impact patient readmission rate for medicare patients. To do this I would most likely perform a regression analysis of readmission rate for each hospital/care system and their corresponding care metrics. Understanding the relationships between patient readmission and quality of care could also help policymakers adjust provider and insurer incentive structures to prioritize the health of individuals.

### Related Work: 
&nbsp;&nbsp;&nbsp;&nbsp; There has been some research done about hospital readmission rate that is tangential to the analysis I am aiming to complete. A paper published in 2020 found that looking at a specific subset of care quality measures, specifically patient satisfaction, leads to lower readmissions rates (Chen et al., 2020). Similarly, the Agency for Healthcare Research and Quality came out with a Re-Engineered Discharge toolkit that predicts a hospital’s readmission rate based on their member mix. While both of these resources analyze how certain healthcare factors affect a hospital’s readmission rate, I would like to examine this issue with a more comprehensive view. This project will be a multi-faceted approach to examining readmission rates using both clinical factors like timeliness while also incorporating structural aspects such as hospital funding sources and the type of hospital.

### Research Questions: 
In order to explore the relationship between hospital quality of care metrics and their patients’ corresponding readmissions rates, I will base my analysis on the following questions: 
* What are the current patterns and distributions of patient readmission rates across the Medicare hospitals and how do they vary by hospital type, funding source, size and location? 
* What quality of care metrics, like timeliness, patient experience, and emergency room wait times are most strongly associated with readmission rate?
* How effective can a multivariate regression model predict readmission rates based on the available quality of care metrics and structural aspects of the hospitals, and how does this prediction power compare across the different types of hospitals?



### Data Sources:  
&nbsp;&nbsp;&nbsp;&nbsp;All data collected for this project came [data.cms.gov](data.cms.gov). First of which is the [Hospital General Information dataset](https://data.cms.gov/provider-data/dataset/xubh-q36u#overview) which contains information on all hospitals that have registered with Medicare. Some of the information in this dataset includes address, type of hospital, ownership type (i.e. non-profit, government) and overall rating. Next I will be using the [Hospital Readmissions Reduction Program (HRRP)](https://data.cms.gov/provider-data/dataset/9n3s-kdb3) dataset, which includes information about the number of discharges, number of readmissions, and ratio of readmissions for each facility that is registered with Medicare. The readmission rate would be the outcome variable for the predictive model. Next, I will be using the [Timely and Effective Care](https://data.cms.gov/provider-data/dataset/yv7e-xc69) table that contains information on how hospitals perform on a variety of clinical measures like average time patients wait to be seen in the emergency department and appropriate care rating given to patients with sepsis. These measures are available for each of the hospitals that are registered with Medicare, so the measure ratings could be used as predictors for readmission rate. The license for all of these data sets is not explicitly stated, but according to an FAQ guide for using data from data.cms.gov, “Works of the U.S. Government are in the public domain and you don’t need permission to reuse them, but an attribution to the agency as the source is appreciated.” 

This analysis is being done in November 2025. Data version information is as follows: 

| Table | Last Updated | Release Date | 
| -------- | ------- | ------- |
| Hospital General Information | 07-16-2025 | 08-06-2025 |
| Hospital Readmissions Reduction Program | 01-08-2025 | 08-06-2025 |
| Timely and Effective Care | 07-24-2025 | 08-06-2025 |

### Methodology: 
&nbsp;&nbsp;&nbsp;&nbsp;In order to carry out the investigation outlined in the research questions section of this plan, I will do the following. First, I will do an exploratory analysis of the data and analyze the distribution of readmission rates and sizes across all registered Medicare hospitals. This will help establish a baseline understanding of the data that can be referenced along with my further analyses.  
&nbsp;&nbsp;&nbsp;&nbsp;Next, to answer the second research question about identifying which quality of care metrics are most associated with large readmission rates, I will perform a correlation analysis. This will identify which, if any, of the quality of care metrics are correlated with readmissions and whether or not that correlation is positive or negative. In the case there are many correlated predictor variables I will use LASSO to select only a subset of the most important variables. Important meaning the variables that explain the most variability in the outcome variable.   
&nbsp;&nbsp;&nbsp;&nbsp;Finally, to address the third research question, I will fit a multivariate logistic regression model as well as a random forest model with the quality of care and hospital-specific variables as the predictors. I will compare the R^2, RMSE and MAE values across both model types to evaluate which is the better predictor. Similarly, I will evaluate the models for interpretability.

### Results: 
To be updated. 
