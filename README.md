# Parkinson's Analysis and Prediction

This project aims to analyze and predict Parkinson's disease using a dataset with various vocal features. The analysis involves data preprocessing, feature extraction, and machine learning model implementation to predict the presence of Parkinson's disease.

## Table of Contents
- [Dataset](#dataset)
- [Dependencies](#dependencies)
- [Key Steps](#key-steps)
  - [Data Import and Exploration](#data-import-and-exploration)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Analysis](#feature-analysis)
  - [Model Training and Evaluation](#model-training-and-evaluation)
- [Results](#results)

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

1. Analyze important parameters such as Jitter, Shimmer, and HNR.

### Model Training and Evaluation

1. Split the dataset into training and testing sets.
2. Train machine learning models and evaluate their performance using metrics like accuracy, mean squared error, and confusion matrix.

### Results

The results section includes the performance metrics of the trained models and visualizations of the results.

#### Performance Metrics

- **Accuracy**: ```90.40%```
- **Mean Squared Error**: ```8.54```
- **Confusion Matrix**: ![image](https://github.com/user-attachments/assets/5da8df35-0880-4c0f-aa93-e0c0198b381e)


#### Visualizations

Below are some key visualizations that illustrate the performance of the models and insights from the data:

1. **Distribution of Jitter, Shimmer, and HNR**  
   ![Jitter, Shimmer, and HNR Distribution](path/to/jitter_shimmer_hnr_distribution.png)

2. **Confusion Matrix Visualization**  
   ![Confusion Matrix](path/to/confusion_matrix.png)

3. **Model Performance Comparison**  
   ![Model Performance](path/to/model_performance_comparison.png)

Feel free to add more visualizations or graphs as necessary to effectively communicate your results.
