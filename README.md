# Wave Energy Converter Farm Analysis and Prediction

## Project Overview
This project focuses on analyzing and predicting the total power output (`Powerall`) of wave energy converter (WEC) farms located in four Australian cities: Adelaide, Sydney, Tasmania, and Perth. The dataset comprises measurements from individual wave energy converters in these farms.
# WEC-ML-Project

## Dataset Description
The dataset contains rows of data for each wave energy converter, with each row consisting of the following elements:
- 16 `x` coordinates (ranging from 0 to 566 meters)
- 16 `y` coordinates (ranging from 0 to 566 meters)
- 16 power values (`p1` to `p16`) for each converter
- A total power value (`Powerall`) for all 16 converters in a farm

## Data Preprocessing
- **Column Naming**: The columns in the dataset were appropriately named for better understanding and manipulation.
- **Data Cleaning**: Rows where `Powerall` was not the sum of `p1` to `p16` were identified as erroneous and removed from the dataset.

## Model Testing
Several machine learning models were tested on the dataset:
- Linear Regression
- Decision Tree
- Random Forest
- XGBoost
- LGBM Regressor

XGBoost emerged as the best-performing model based on our evaluations.

## Experiments and Findings
1. **Combining Datasets**: An initial approach combined datasets from all cities into one large dataset for training. However, significant discrepancies in the data values led to suboptimal results.
   
2. **PCA Application**: A hypothesis was tested where `x` and `y` coordinates (`xn` and `yn`) were combined using Principal Component Analysis (PCA), reducing the 32 features into 16. This approach aimed to leverage the strong correlation between these coordinates as they represent points of a single converter.

3. **Data Pipelines**: Data processing pipelines were created for efficient data handling and to facilitate further experiments.

4. **City-wise Testing with and without PCA**: Each city's dataset was tested with and without the PCA application. It was found that for three cities, the PCA approach yielded better results. However, for Perth, the PCA approach was less effective due to smaller data range and significant noise.

## Final Results
The best models were tested on unseen data, achieving an average Root Mean Square Error (RMSE) of 22,500. This is considered an excellent outcome, given the scale of `Powerall`, which extends into millions.

## Conclusion
This project demonstrates the effective use of machine learning techniques in predicting the total power output of wave energy converter farms. The application of PCA and tailored approaches for different cities were key to the success of the model predictions.
