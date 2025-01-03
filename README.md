# README : Weather Classifier

This project is a weather classifier that categorizes weather conditions into five classes: **Drizzle**, **Fog**, **Rain**, **Snow**, and **Sun**. The classification model uses a **Random Forest Classifier**, and key techniques like **log1p transformation** for handling skewness and **hyperparameter tuning** to improve model performance. The dataset has imbalanced class labels, and efforts were made to improve recall, precision, and F1 scores for the minority classes.

## Table of Contents
1. [Overview](#overview)
2. [Data Preprocessing](#data-preprocessing)
3. [Modeling](#modeling)
4. [Hyperparameter Tuning](#hyperparameter-tuning)
5. [Evaluation Metrics](#evaluation-metrics)
6. [Results](#results)
7. [Conclusion](#conclusion)
8. [Usage](#usage)

## Overview
The weather classifier categorizes the input data into one of the following weather conditions:
- **0**: Drizzle
- **1**: Fog
- **2**: Rain
- **3**: Snow
- **4**: Sun

### Key Features:
- Random Forest Classifier used for prediction.
- Log1p transformation applied to handle skewness in data.
- Hyperparameter tuning was employed to optimize the classifier's performance.
- Focus on improving recall, precision, and F1 scores for minority classes.

## Data Preprocessing
Before training the model, the following preprocessing steps were performed:
- **Log1p Transformation**: Applied to handle skewness in features.
- **Handling Class Imbalance**: The dataset had unbalanced class labels, with the majority classes being **Sun** and **Rain**. Class imbalance was addressed through tuning and model optimization.
- **Feature Selection and Engineering**: Ensured the most relevant features were fed into the model to improve its accuracy.

## Modeling
A **Random Forest Classifier** was chosen as the model for weather classification due to its robustness, ability to handle complex data, and inherent capability to deal with overfitting. The model was initially trained without hyperparameter tuning, and later fine-tuned to improve its performance.

## Hyperparameter Tuning
Hyperparameter tuning was performed using **GridSearchCV** to optimize the Random Forest model. The following parameter grid was used to find the best hyperparameters:
- Number of estimators (`n_estimators`)
- Maximum depth of trees (`max_depth`)
- Minimum samples per leaf (`min_samples_leaf`)
- Maximum features (`max_features`)
- Whether bootstrap samples are used (`bootstrap`)
- Weights associated with classes (`class_weight`)

## Evaluation Metrics
The following evaluation metrics were used to assess the model's performance:
- **Classification Report**: Provides precision, recall, and F1-score for each class.
- **Cross-validation**: To evaluate model stability across multiple splits of the data.
- **ROC-AUC Scores**: To assess the model's ability to discriminate between classes.

## Results

### Classification Report Before Hyperparameter Tuning:
| Class        | Precision | Recall | F1-Score | Support |
|--------------|-----------|--------|----------|---------|
| 0 (Drizzle)  | 1.00      | 0.22   | 0.36     | 9       |
| 1 (Fog)      | 0.75      | 0.24   | 0.36     | 25      |
| 2 (Rain)     | 0.94      | 0.93   | 0.93     | 120     |
| 3 (Snow)     | 0.33      | 0.12   | 0.18     | 8       |
| 4 (Sun)      | 0.80      | 0.99   | 0.89     | 131     |

**Accuracy**: 0.85  
**Macro Average**: Precision: 0.77, Recall: 0.50, F1-Score: 0.55  
**Weighted Average**: Precision: 0.85, Recall: 0.85, F1-Score: 0.83

### Classification Report After Hyperparameter Tuning:
| Class        | Precision | Recall | F1-Score | Support |
|--------------|-----------|--------|----------|---------|
| 0 (Drizzle)  | 0.36      | 0.44   | 0.40     | 9       |
| 1 (Fog)      | 0.55      | 0.44   | 0.49     | 25      |
| 2 (Rain)     | 0.96      | 0.91   | 0.94     | 120     |
| 3 (Snow)     | 0.62      | 0.62   | 0.62     | 8       |
| 4 (Sun)      | 0.82      | 0.89   | 0.85     | 131     |

**Accuracy**: 0.84  
**Macro Average**: Precision: 0.67, Recall: 0.66, F1-Score: 0.66  
**Weighted Average**: Precision: 0.84, Recall: 0.84, F1-Score: 0.84

### Key Improvements:
- **Recall and F1-Score** for minority classes (Drizzle, Fog, and Snow) were significantly improved after hyperparameter tuning.
- **Precision** for most classes remained stable or slightly improved.
- Overall **accuracy** remained consistent around 84%-85%, but the model’s ability to classify minority classes improved.

## Conclusion
The weather classifier demonstrates strong performance in classifying different weather conditions using a Random Forest model. The application of **log1p transformation** and **hyperparameter tuning** effectively addressed the issues of skewness and class imbalance, leading to better classification metrics, especially for minority classes like **Drizzle**, **Fog**, and **Snow**.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/weather-classifier.git
