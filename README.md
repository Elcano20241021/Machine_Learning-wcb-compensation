# NY WCB Injury Claim Prediction – Machine Learning Project
Repository for the **Machine Learning** course in the Master's program *Data Science and Advanced Analytics (2024/2025)* at **NOVA IMS**.

## Project Overview

This project aims to assist the **New York Workers’ Compensation Board (WCB)** in automating workplace injury claim assessments. The primary goal is to enhance **decision efficiency**, **reduce manual inconsistencies**, and improve **resource allocation**.

The dataset includes over **590,000 claims**, featuring details on injury types, industries, wage info, and claim decisions. The task is to predict the most appropriate classification outcome based on available features.

## Techniques & Methodology

We applied **supervised machine learning** with multiple models, including:

- Decision Tree  
- Random Forest  
- Gradient Boosting  
- XGBoost  
- CATBoost  

To address severe class imbalance, we used **ADASYN** (Adaptive Synthetic Sampling) to balance the training data.

However, we observed that although **Random Forest** achieved the **best F1 score on the test set (0.3334)**, it did not consistently generalize across validation folds during cross-validation. We suspect that **ADASYN** may have introduced **overfitting on synthetic patterns**, and further investigation is being conducted into the interaction between resampling and tree-based models.

See comparison table of Macro F1 scores below:

| Model        | F1 Train | F1 Validation | F1 Test | Notes |
|--------------|----------|----------------|---------|-------|
| Decision Tree | 0.3094   | 0.3214         | 0.2234  | Baseline |
| Gradient Boosting | 0.3562 | 0.3707       | 0.2515  | - |
| **Random Forest** | **0.3658** | **0.3818** | **0.3334** | Best Test F1 |
| XGBoost      | 0.3637   | 0.3986         | 0.3079  | Strong CV |
| CATBoost     | 0.3772   | 0.3500         | 0.2473  | Lower generalization |

## Youtube
Watch our model prediction interface in action:  
[Web Application Demo](https://www.youtube.com/watch?v=lomxaOXgKUY)

Built using **Streamlit**, this app enables users to simulate real-time claim predictions based on input features — demonstrating the operational value of machine learning in decision support systems.

## Contributors

- [20211561@novaims.unl.pt](https://github.com/diogokursi/ML2425/commits?author=diogokursi)
- [20241433@novaims.unl.pt]
- [20240333@novaims.unl.pt]
- [20240694@novaims.unl.pt]
