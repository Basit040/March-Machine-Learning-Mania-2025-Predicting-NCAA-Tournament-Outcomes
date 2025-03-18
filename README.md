# March-Machine-Learning-Mania-2025-Predicting-NCAA-Tournament-Outcomes
This repository contains my solution for the March Machine Learning Mania 2025 Kaggle competition. The goal of the competition is to forecast the outcomes of both the Men's and Women's 2025 NCAA Division I basketball tournaments by submitting predictions for every possible tournament matchup.
## Competition Description
Another year, another chance to predict the upsets, call the probabilities, and put your bracketology skills to the leaderboard test. In our eleventh annual March Machine Learning Mania competition, Kagglers will once again join the millions of fans who attempt to predict the outcomes of this year's college basketball tournaments. Unlike most fans, you will pick the winners and losers using a combination of rich historical data and computing power, while the ground truth unfolds on television.

You are provided data of historical NCAA games to forecast the outcomes of the Division 1 Men's and Women's basketball tournaments. This competition is the official 2025 edition, with points, medals, prizes, and basketball glory at stake.

We have reverted back to the format from 2023 where you are making predictions about every possible matchup in the tournament, evaluated using the Brier score. Prior to the start of the tournaments, the leaderboard of this competition will reflect scores from 2021-2024 only. Kaggle will periodically fill in the outcomes and rescore once the 2025 games begin.

# Approach
1. Data Preparation
Data Loading: The datasets include historical game results, team information, seeds, and other relevant features for both Men's and Women's tournaments.

## Feature Engineering:

Created features such as seed differences, score differences, and aggregated statistics (e.g., average scores, win rates).

Combined Men's and Women's datasets to leverage shared patterns.

Handling Missing Data: Used SimpleImputer to fill missing values and StandardScaler to normalize features.

## Exploratory Data Analysis (EDA)
Visualized key insights such as:

Win distribution by seed matchups.

Score distribution of winning and losing teams.

Win rate by seed for Men's and Women's teams.

Upset rates over the years.

Correlation between features using heatmaps.

Investigated differences between Men's and Women's teams, such as average score differences and win rates by seed.

## Modeling
Ensemble Model: Used a VotingClassifier to combine predictions from multiple models:

XGBoost (XGBClassifier): A powerful gradient-boosting algorithm.

Random Forest (RandomForestClassifier): An ensemble of decision trees.

Logistic Regression (LogisticRegression): A linear model for binary classification.

Training: Trained the ensemble model on historical game data to predict the probability of a team winning a matchup.

Evaluation: Evaluated the model using metrics such as:

Log Loss: Measures the performance of the classification model.

Brier Score: Evaluates the accuracy of probabilistic predictions.

Mean Absolute Error (MAE): Measures the average error in predictions.

## Submission
Generated predictions for every possible tournament matchup.

Saved the predictions in the required format for submission to Kaggle.

# Code Structure
## 1. Data Loading and Preprocessing
Loaded datasets using glob and combined Men's and Women's data.

Created features such as SeedDiff, ScoreDiff, and aggregated statistics.

Handled missing values and normalized features.

## 2. Exploratory Data Analysis (EDA)
Visualized key insights using matplotlib and seaborn.

Compared Men's and Women's teams using histograms, box plots, and scatter plots.

## 3. Model Training
Used VotingClassifier to combine predictions from XGBClassifier, RandomForestClassifier, and LogisticRegression.

Trained the model on historical game data and evaluated it using cross-validation.

## 4. Prediction and Submission
Generated predictions for all possible matchups.

Saved the predictions in a CSV file for submission.
