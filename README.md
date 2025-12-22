📀 DVD Rental Duration Prediction

Technical Report

Summary

The objective of this project was to develop a machine learning model capable of predicting how many days a customer will keep a DVD, enabling a rental company to optimize inventory planning.
The key performance requirement was to achieve a Mean Squared Error (MSE) ≤ 3.0.
Using a Baseline vs. Challenger modeling strategy, the Random Forest Regressor emerged as the superior model, achieving an MSE of 2.0301, significantly exceeding the project goal.

 1. Data Preparation & Feature Engineering

The raw dataset (rental_info.csv) required several transformations to make it suitable for regression modeling:

🔹 Target Variable Engineering
rental_length_days was derived from the difference between rental and return timestamps.

🔹 Text Feature Processing
The special_features column was parsed to create binary indicator variables:

deleted_scenes
behind_the_scenes

This enabled the model to interpret movie content attributes numerically.

🔹 Data Leakage Prevention

Raw date columns (e.g., return timestamps) were removed.
Including the return date would leak the target variable and invalidate real-world predictions.

 2. Experimental Design

To ensure a fair and interpretable comparison, two models were evaluated:

📉 Baseline Model — Linear Regression
Simple and interpretable

Assumes linear relationships between features and rental duration
🌲 Challenger Model — Random Forest Regressor

Captures non-linear relationships
Ensemble of 100 decision trees
Reduces variance through averaging

📊 3. Performance Comparison

Models were evaluated on a 20% hold-out test set unseen during training.

Model	Mean Squared Error (MSE)	Performance vs. Goal
Linear Regression	2.9417	✅ Pass (Borderline)
Random Forest	2.0301	✅ Pass (Excellent)

📈 Result:
The Random Forest model outperformed the baseline by approximately 31%, demonstrating its ability to capture complex rental behavior patterns.

💡 4. Key Business Insights
Feature importance analysis from the Random Forest model revealed:

💰 Price-Driven Behavior

Amount paid and rental rate are the strongest predictors of rental duration.
Customers appear to adjust how long they keep DVDs based on cost considerations.

🎬 Content Has Limited Impact

Features such as:
Movie length
Release year
Special features
have minimal influence compared to financial variables.

 Implication: Pricing strategy plays a larger role in rental duration than movie characteristics.

✅ 5. Final Recommendation
Recommend deploying the Random Forest Regressor for operational inventory planning.

🚀 Why Random Forest?

Achieves high predictive accuracy (MSE = 2.03)
Robust to non-linear customer behavior
Improves stock availability forecasts
Enhances customer satisfaction
Supports data-driven purchasing decisions

📎 Project Highlights

Modeling Approach: Baseline vs. Challenger
Evaluation Metric: Mean Squared Error (MSE)
Best Model: Random Forest Regressor
Business Value: Improved inventory optimization

🔍 Summary

This project demonstrates how machine learning can transform transactional rental data into actionable business insights, with pricing emerging as the dominant driver of customer rental behavior.
