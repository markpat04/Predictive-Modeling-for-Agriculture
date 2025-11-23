# Project Overview
**Business Context:** In agriculture, maximizing yield is crucial for profitability. However, soil analysis—measuring Nitrogen (N), Phosphorous (P), Potassium (K), and pH—can be expensive and time-consuming. 
Farmers often have budget constraints and need to know which specific metrics are the most critical to track.

**The Goal:** This project aims to assist farmers in selecting the best crop for their field based on soil measurements. Furthermore, we aim to identify the single most important soil feature for predicting crop types. 
This allows farmers to prioritize specific soil tests, saving costs while maintaining high yield potential.

## Data Description
The dataset soil_measures.csv contains soil metrics and the optimal crop for those conditions.

| Feature | Description |
| :--- | :--- |
| **N** | Nitrogen content ratio in the soil |
| **P** | Phosphorous content ratio in the soil |
| **K** | Potassium content ratio in the soil |
| **PH** | pH value of the soil |
| **Crop** | The optimal crop species (Target Variable) |

## Methodology & Approach
We are predicting a categorical variable (Crop Type) based on continuous variables (Soil Metrics). 
Since there are multiple crop types (not just two), we use Multinomial Logistic Regression.

The Feature Importance Strategy
Instead of throwing all data into the model at once, we iterate through each feature individually.

1. **Loop through features:** We isolate N, P, K, and pH one by one.
2. **Train & Test:** For each feature, we train a model and predict outcomes on unseen test data.
3. **Evaluate:** We use the F1-Score to measure success.


## Results
After analyzing the performance of each soil metric, we identified the feature with the strongest predictive power.
Key Finding: Potassium (K) is the single most important feature for predicting the optimal crop type in this dataset.

## Business Conclusion
Based on this analysis, if a farmer is on a strict budget and can only afford to test for one specific nutrient, they should prioritize testing for Potassium (K) levels. 
This single metric provides the highest probability of correctly determining the optimal crop to plant, ensuring better resource management and yield planning.
