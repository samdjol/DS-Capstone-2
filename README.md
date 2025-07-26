# DSCapstone2

A Data-Driven Approach to Player Valuation and Scouting
This project utilizes a dual-model machine learning system to analyze the football transfer market, providing deep insights for player valuation and recruitment. By combining supervised and unsupervised learning, the system moves beyond simple price prediction to offer a robust tool for identifying market inefficiencies and discovering undervalued talent.

Project Overview
The core of this project is a two-part analytical system:

Supervised Prediction Model: A tuned XGBoost Regressor that predicts a player's market value based on a wide range of performance, biographical, and contractual data. With a final R-squared of 0.73, this model effectively replicates the complex logic of expert valuations. Its primary purpose is to challenge the market consensus and identify players whose data-driven value differs significantly from their estimated value.

Unsupervised Clustering Model: A K-Means clustering algorithm that segments players into distinct statistical archetypes based on their career data. This provides a powerful framework for scouting, allowing users to filter for specific player profiles (e.g., "Young Prospects," "Elite Superstars," "Defensive Veterans") before applying the predictive model.

Together, these models create a powerful workflow for identifying "hidden gems"—players who are statistically similar to high-value archetypes but are currently undervalued by the market.

Key Features
Predictive Valuation: An XGBoost model that predicts player market value with 73% accuracy.

Player Segmentation: K-Means clustering to identify distinct player archetypes.

Outlier Detection: Analysis of prediction errors and z-scores to find players the model strongly agrees or disagrees with the market on.

Comprehensive Feature Engineering: Creation of advanced features like quality-adjusted performance stats and an "age curve" metric.

Robust Pipeline: A full scikit-learn pipeline for reproducible preprocessing, training, and evaluation.

Tech Stack
Python 3

Pandas: For data manipulation and analysis.

Scikit-learn: For building the machine learning pipeline, preprocessing, and modeling (Linear Regression, Random Forest, K-Means).

XGBoost: For the final, high-performance predictive model.

Matplotlib & Seaborn: For data visualization and analysis.

Joblib: For model serialization (pickling).

How to Use
Data Preparation: Ensure your raw CSV files are in the correct directory. Run the initial data cleaning and merging notebooks to produce the final model_df.

Train and Evaluate Models: Use the main analysis notebook to run the fit_evaluate_and_tune_model function. This will train, tune, and evaluate the models, printing the performance metrics.

Analyze Clusters: Run the K-Means clustering notebook to segment players and analyze the resulting archetypes.

Find Outliers: Use the error analysis script to identify players with the largest prediction discrepancies, which represent potential scouting targets.

Make New Predictions: Load the saved player_value_model.pkl file using joblib to make predictions on new, unseen player data.

Key Findings
The final tuned XGBoost Regressor was the best-performing model, achieving an R-squared of 0.73 on the test set.

The most important drivers of market value were found to be league/club prestige, contract status, age, and quality-adjusted performance stats.

The K-Means algorithm successfully identified 10 distinct player archetypes, providing a powerful framework for targeted scouting.

The model was most effective when trained on the log-transformed target variable, which helped to normalize the skewed distribution of player values.

Future Work
Incorporate More Granular Data: Add advanced stats like "Expected Goals (xG)" and detailed injury history to improve accuracy.

Advanced Feature Engineering: Use techniques like target encoding for high-cardinality features.

Deployment: Develop an interactive dashboard (e.g., using Streamlit or Dash) to allow users to filter clusters and explore player valuations in real-time.
