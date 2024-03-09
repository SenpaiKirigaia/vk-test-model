# Model for VK

This project aims to develop a machine learning model for ranking search results using various algorithms, including Gradient Boosting Regressor, XGBRanker, and Random Forest Regressor. The performance of the models is evaluated using the Normalized Discounted Cumulative Gain (NDCG) metric.

## Requirements

To install the required packages, run the following command:

```
pip install -r requirements.txt
```

## Dataset

The dataset used in this project consists of two CSV files: `train_df.csv` and `test_df.csv`. Each file contains 81 columns, including the `search_id`, `target`, and 79 feature columns. The `train_df.csv` file has 15,081 rows, and the `test_df.csv` file has 1,529 rows.

## Preprocessing

The data is preprocessed by handling missing values and normalizing the features using `StandardScaler` from `sklearn.preprocessing`. Additionally, Principal Component Analysis (PCA) is applied to reduce the dimensionality of the feature space.

## Models

### 1. Gradient Boosting Regressor

The Gradient Boosting Regressor is trained using a random search approach to find the best hyperparameters. The model is evaluated on the test set, and the NDCG score is reported.

### 2. XGBRanker

XGBRanker is a specialized algorithm for ranking tasks. It is trained using a random search approach, and the best hyperparameters are selected based on the NDCG score.

### 3. Random Forest Regressor

The Random Forest Regressor is also trained using a random search approach, and the best hyperparameters are selected based on the NDCG score.

## Feature Importance

The feature importances are analyzed for the Gradient Boosting Regressor and XGBRanker models. The top 23 most important features are identified, and the models are retrained using only these features.

## Results

The different models achieve the following NDCG scores:

- Gradient Boosting Regressor: 0.6736
- XGBRanker: 0.6606
- Gradient Boosting Regressor with top 23 features: 0.6707
- XGBRanker with top 23 features: 0.6606
- Random Forest Regressor: 0.6063

The Gradient Boosting Regressor achieved the highest NDCG score of 0.6736, closely followed by the XGBRanker model with a score of 0.6606. Reducing the feature space to the top 23 most important features slightly improved the performance of the Gradient Boosting Regressor but did not affect the XGBRanker model significantly.

## Conclusion

This project demonstrates the application of various machine learning algorithms for ranking search results. The Gradient Boosting Regressor and XGBRanker models outperformed the Random Forest Regressor in terms of the NDCG metric. Feature selection using the top 23 most important features slightly improved the performance of the Gradient Boosting Regressor model.
