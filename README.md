# Parkinson's Analysis and Prediction

This project aims to analyze and predict Parkinson's disease using a dataset with various vocal features. The analysis involves data preprocessing, feature extraction, and machine learning model implementation to predict the presence of Parkinson's disease. Here, `total_UPDRS` shows the extent of Parkinson's Disease.

## Table of Contents
- [Results](#results)
- [Dataset](#dataset)
- [Dependencies](#dependencies)
- [Key Steps](#key-steps)
  - [Data Import and Exploration](#data-import-and-exploration)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Analysis](#feature-analysis)
  - [Model Training and Evaluation](#model-training-and-evaluation)
- [Observations](#observations)

### Results

The results section includes the performance metrics of the trained models and visualizations of the results.

#### Performance Metrics

- **Accuracy**: 90.40%
- **Mean Squared Error**: 8.54

- **Confusion Matrix Visualization**  
  <img src="https://github.com/user-attachments/assets/5da8df35-0880-4c0f-aa93-e0c0198b381e" alt="Confusion Matrix" width="300"/>

#### Visualizations

Below are some key visualizations that illustrate the performance of the models and insights from the data:

1. **Distribution of Jitter, Shimmer, and HNR**  
   <img src="https://github.com/user-attachments/assets/b66cc90f-af7e-4466-b1f1-ead3c3589b33" alt="Jitter vs Shimmer Graph" width="300"/>

2. **Age vs Jitter vs Shimmer Graph**  
   <img src="https://github.com/user-attachments/assets/4724d722-c5e7-4ebb-b1a7-ab1fe484a34e" alt="Age vs Jitter vs Shimmer" width="300"/>

3. **Relation with Age and Sex**  
   <img src="https://github.com/user-attachments/assets/7f696562-8b8b-4e75-894d-b213aa3d10ef" alt="Relation with Age and Sex 1" width="300"/>  
   <img src="https://github.com/user-attachments/assets/a1a450e6-535f-40aa-a946-afaeb04f1195" alt="Relation with Age and Sex 2" width="300"/>

4. **UPDRS vs Age and vs Sex**  
   <img src="https://github.com/user-attachments/assets/70e0e4e8-0a0c-416d-8828-3abee0bb6a05" alt="UPDRS vs Age and Sex" width="300"/>

5. **Final Relation Graph between UPDRS and Age**  
   <img src="https://github.com/user-attachments/assets/6a16cb43-cd51-4a95-a89b-bd1ef25d278b" alt="UPDRS vs Age" width="300"/>

6. **Feature Importances**  
   <img src="https://github.com/user-attachments/assets/a031c18e-72e7-45d3-a54e-939eb171fcc7" alt="Feature Importances" width="300"/>

7. **Model Performance Comparison**  
   <img src="https://github.com/user-attachments/assets/5a4ffb50-148f-4112-a482-9ead27042f5b" alt="Model Performance Comparison" width="300"/>


## Dataset

The dataset contains various vocal features that are important for the analysis and prediction of Parkinson's disease. Some of the key features include:

- **Jitter**: Measures of frequency variation in consecutive periods of a sound waveform.
- **Shimmer**: Measures of amplitude variation in consecutive periods.
- **Harmonic-to-Noise Ratio (HNR)**: Measures the ratio of harmonic sound to noise in a voice signal.
- Several other voice signal parameters.

The dataset is loaded from a CSV file named `better_data.csv`.

## Dependencies

The following libraries are required to run the notebook:

- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn

## Key Steps

### Data Import and Exploration

1. Load the dataset from `better_data.csv`.
2. Display the first few rows to understand the structure of the data.

```python
park = pd.read_csv("better_data.csv")
park.head()
```

### Data Preprocessing
Drop unnecessary columns, such as test_time.
```python
park.drop(columns=['test_time'], inplace=True)
```
### Feature Analysis

Analyze important parameters such as Jitter, Shimmer, and HNR.

### Model Training and Evaluation

1. Split the dataset into training and testing sets.
2. Train machine learning models and evaluate their performance using metrics like accuracy, mean squared error, and confusion matrix.
3. **Algorithms Used**:
   - Linear Regressor
   - Elastic Net Regressor
   - Random Forest Regressor

4. **Other Techniques Used**:
   - Principal Component Analysis (PCA)
   - Feature Importance Extraction
   - Training based on top features


## Observations

### PCA (Principal Component Analysis)

I observed that applying PCA to reduce the dimensionality from 15 features to 1 might not be very beneficial. It seems that PCA is more effective when dealing with a larger number of features.

### Combining UPDRS Scores

I decided to combine "total_UPDRS" and "motor_UPDRS" into "combined_UPDRS" as a feature engineering step. This simplifies the target variable for regression modeling.

### Model Evaluation

I used evaluation metrics (MSE, RMSE, MAE, R2) to gain insights into the performance of different regression models, such as Linear Regression, Elastic Net, and Random Forest. Random Forest Regression appeared to perform well, especially based on the R2 score.

### Feature Importance

Analyzing feature importance, particularly the bar chart, helped me identify the features that contribute the most to the model's predictions. Age stood out as the most important feature, aligning with the understanding that Parkinson's disease is more common in older individuals.

- **Best performing scenario till now**: Random Forest Regressor, after applying Feature Importance

### Visualization

I created scatter plots, strip plots, and pair plots to visually represent relationships between different variables. These visualizations are crucial for my understanding of the patterns in the data.

### Decision Tree Visualization

Visualizing decision trees from the random forest models provided insights into how the model makes predictions. This was helpful for interpretability.

### Model Comparison

I compared the performance of Linear Regression, Elastic Net, and Random Forest Regression. It's important to consider the trade-offs between model complexity and performance.

### Avoiding Feature Combination

I chose not to combine all jitter variables into one, considering the slight degradation in the performance of the Random Forest Regressor.
