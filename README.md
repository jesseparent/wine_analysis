# Wine Quality Dataset Analysis

## Overview
This project aims to analyze the Wine Quality dataset to predict the quality of red wines based on various physicochemical properties, excluding the features **free sulfur dioxide** and **color**. The dataset provides an opportunity to build predictive models for wine quality using regression techniques.

## Dataset
The dataset is sourced from the UC Irvine Machine Learning Repository and consists of physicochemical tests of wine samples and quality ratings given by experts.

### Features
The dataset, after the removal of the **free sulfur dioxide** and **color** feature, includes the following physicochemical attributes:
- **fixed acidity**: Acid in the wine that does not evaporate.
- **volatile acidity**: Amount of acetic acid in the wine, which can lead to an unpleasant vinegar taste.
- **citric acid**: A natural preservative that also adds a fresh taste.
- **residual sugar**: The amount of sugar remaining after fermentation.
- **chlorides**: The amount of salt in the wine.
- **total sulfur dioxide**: Total amount of sulfur dioxide present.
- **density**: The density of the wine (g/cm³).
- **pH**: The acidity of the wine.
- **sulphates**: A wine additive that can lead to sulfur dioxide levels, impacting quality.
- **alcohol**: The alcohol content of the wine (% volume).
- **quality**: The quality rating assigned by experts (integer values ranging from 0 to 10).

### Reasons for Feature Removal
1. **Color Features**: The analysis focuses on the physicochemical properties of the wine without including color parameters to evaluate the intrinsic qualities affecting wine quality. Removing color features allows for a more straightforward analysis of how these other attributes influence quality ratings.
2. **Free Sulfur Dioxide**: This feature was dropped due to the potential for multicollinearity with the **total sulfur dioxide** feature. By eliminating it, we aim to simplify the model, reduce redundancy, and enhance interpretability without significantly affecting the dataset's predictive power.

## Objective
The primary goal of this project is to develop predictive models that accurately predict the wine quality using regression techniques. While the dataset contains ordinal quality ratings, we will be treating the quality as a binary outcome when necessary (e.g., classifying wines as "high quality" vs. "low quality") due to the absence of a continuous measurement (like speed) in the dataset.
Specifically, we will use the following bins for classification:
- **Quality 0**: Considered as "Low Quality"
- **Quality 1**: Considered as "High Quality"

## Resampling Techniques
To address class imbalance in the dataset, we utilize resampling techniques:
- **SMOTE (Synthetic Minority Over-sampling Technique)**: This technique generates synthetic samples for the minority class, helping to balance class distributions in the dataset.
- **SMOTEENN (SMOTE + Edited Nearest Neighbors)**: This combines SMOTE with Edited Nearest Neighbors to not only generate synthetic samples but also to clean the majority class by removing noisy instances.

## Models Used
We employ various machine learning algorithms to achieve this objective, including:
  1. **Random Forest Regressor**
  2. **XGboost model**
  3. **Logistic Regression** (for binary outcomes)
  4. **LGBMClassifier**
  5. **SVC**
  6. **KNeighborsClassifier**
  7. **GradientBoostingClassifier**
  8.**MLPClassifier**


## Pipeline Overview
1. **Data Loading**: Loading the dataset using Pandas.
2. **Data Preprocessing**: Including scaling and splitting the dataset into training and testing datasets.
3. **Model Training**: Training different models and evaluating their performance using accuracy metrics and classification reports.
4. **Feature Importance**: Analyzing the most and least important features affecting wine quality predictions.
5. **Hyperparameter Optimization**: Optimizing hyperparameters for the models using Grid Search.


## Results
The results of the analysis will include:
- Model accuracies and classification reports.
- Visualizations of feature importances.
- Insights on the physicochemical properties that most influence wine quality (see a conclusion)

## Conclusions
- Insights derived from the model performance and feature importances could guide future efforts in wine production, quality control, and improvements in wine characteristics.
- The choice of regression techniques, even with a binary output approach, highlights the flexibility in analyzing ordinal data and deriving meaningful predictions.

## License
This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.
