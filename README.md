# AIT511-Machine-Learning-Course-Project-2
Forest Cover Type Classification using Machine Learning
A Machine Learning Analysis of Environmental and Terrain Indicators for Predicting Forest Cover Types

Author: Rohitangshu Bose (MT2025106)
Course: Machine Learning — IIIT Bangalore

📌 Project Overview

This project develops machine learning models to predict seven forest cover types using the UCI Forest Cover Type dataset, consisting of 581,012 samples and 54 environmental, terrain, and soil features.

The study follows a full ML workflow:

Exploratory Data Analysis (EDA)

Data preprocessing and SMOTE balancing

Model training using ANN, Logistic Regression, and Linear SVM

Performance comparison

Visual interpretation of the dataset and model behaviour

A detailed project report (in LaTeX) accompanies this repository.

📂 Dataset Summary

The dataset contains:

54 features, including

Elevation, slope, aspect

Hydrology distances

Hillshade values

40 soil type indicators

4 wilderness area indicators

7 target classes representing forest cover types

581,012 total samples

The target variable is mapped from 1–7 to 0–6 for modeling.

🔎 Exploratory Data Analysis (EDA)
Key findings:
1. Severe Class Imbalance

Cover Types 1 and 2 dominate the dataset

Classes 3–7 represent only ~1–4% each

SMOTE is required for fair model training

2. Feature Distribution Patterns

Elevation shows strong multimodality → ecological subregions

Hydrology & roadway distances show long right-skewed tails

Aspect follows a U-shaped directional pattern

Hillshade values are close to Gaussian

3. Correlation Insights

Most features have weak correlations → high-dimensional, nonlinear structure

Hillshade 9am & 3pm are strongly negatively correlated (–0.77)

Elevation correlates moderately with distance to roadways

4. Ecological Separation in Feature Space

A scatter plot of Elevation vs Hydrology Distance reveals distinct clusters per cover type, confirming nonlinear separability.

⚙️ Preprocessing Pipeline

Removal of missing labels

Standardization of continuous features using StandardScaler

Application of SMOTE to training data to handle imbalance

Train–test split with stratification

SMOTE + scaling proved essential for model stability and performance.

🤖 Models Trained
1. Artificial Neural Network (ANN)

Fully connected network

Batch Normalization + Dropout

SMOTE-balanced training

Best overall results

2. Logistic Regression

Baseline linear classifier

Struggles with nonlinear patterns and imbalance

3. Linear SVM (SGDClassifier)

Slight improvement over LR

Still unable to model complex ecological structure

📊 Model Performance
Model	Accuracy	Macro F1	Weighted F1
ANN	0.9037	0.8611	0.9067
Logistic Regression	0.8238	0.6611	0.8102
Linear SVM	0.8139	0.6212	0.7947
Why ANN Performs Best

Captures nonlinear relations in terrain–ecology space

Resilient to class imbalance (with SMOTE)

Regularization stabilizes training

Learns multi-feature interactions not visible in linear models

🖼️ Visualizations Included

The repository includes all EDA and evaluation figures:

Class distribution

Histograms

Boxplots by cover type

Correlation heatmap

Scatter plots

ANN training curves

Confusion matrices (ANN, LR, SVM)

Model comparison chart

These visuals provide deep insight into dataset structure and model behaviour.

🧠 Key Takeaways

Elevation and hydrology distance are among the strongest predictors.

The dataset is highly nonlinear, limiting the effectiveness of LR and linear SVM.

ANN significantly outperforms classical models when combined with scaling + SMOTE.

The problem benefits from models that can learn complex ecological interactions.

📄 Project Report

The complete LaTeX report (matching the official course project format) is available in the repository.

🚀 Future Improvements

Potential extensions include:

Random Forest / Gradient Boosting (XGBoost, CatBoost, LightGBM)

CNN or hybrid deep-learning models leveraging terrain structure

Spatial feature engineering

Automated hyperparameter optimization (Optuna / Random Search)
