# CA House Price

## Overview
This project focuses on predicting CA housing close price predictions using a large dataset containing both numerical
and categorical predictors. The goal was to preprocess messy data with mixed data types and missing values
to train a Random Forest model.

The project was originally created as part of a group internship project initiated by Yuxin Liu. 
The original repository was private.
Current version reflects my own preprocessing, modeling, and evaluation work, with notebooks renamed for clarity and organization. All datasets were also removed to respect privacy laws.

## Objectives
- Preprocessed and cleaned a 500k+ row dataset with mixed feature types
- Design separate preprocessing pipelines for numerical and categorical variables
- Trained and evaluated Random Forest models using cross-validation and feature engineering 

## Dataset
The dataset was provided by IDXExchange LLC as part of the internship project and is included in th eoriginal repository,
but to respect usage restrictions, the raw data is not publicly available in this forked repository.

The Jupyter Notebooks assume that the datsets exist, and are under the `data/` folder.

The dataset consists of over 500,000 housing records for homes across California from January 2024 to October 2024.
It contains numerical and categorical variables related to property characteristics and location.
Missing values and categorical encodings were handled during data preprocessing.

## Methods
- Numerical feature cleaning (scaling, missing value handling)
- Categorical feature encoding (one-hot encoding, binary encoding, probabilistic imputation)
- Dataset merging and feature alignment
- Random Forest training and hyperparameter optimization using RandomizedSearchCV and GridSearchCV
- Cross-validation model evaluation to assess generalization performance
- Reproducibility (random seeds, splits)

## Results
Two Random Forest models were trained using hyperparameter tuning via cross-validation (RandomizedSearchCV and GridSearchCV).
The first model was trained on the full dataset (unfiltered), while the second was trained on the dataset with the top and bottom 1%
of observations removed to account for extreme outliers (filtered).

The models trained on the unfiltered dataset had higher RMSE and lower R², indicating that extreme outliers can heavily influence
the error. In contrast, the models trained on the filtered dataset had lower RMSE and higher R².

However, the model trained on the unfiltered dataset performed well when evaluated on filtered test data, so the model
was able to learn the trends well, except in the presence of extreme outliers. This behavior is expected when outliers are present
since tree-based models can be sensitive to large errors.

## Contributions

Hannah Nguyen: Data preprocessing (numerical and categorical), feature engineering, Random Forest model training,
evaluation, and final analysis.

Yuxin Liu, Yukang Wu, Tori Nguyen, Sherry Qian, Bowie Chuang, Rachel Wei: Early exploratory work during initial phase of the project.

## Author
Hannah Nguyen

https://github.com/hnguyennn

https://www.linkedin.com/in/hannah-p-nguyen/
