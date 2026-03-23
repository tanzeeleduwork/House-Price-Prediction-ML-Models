# House Price Prediction - Machine Learning Implementation

A complete machine learning project demonstrating targeted feature engineering, model selection, and evaluation techniques for predicting California house prices.

## Project Overview

This project builds a predictive model for house prices using ensemble learning methods and three strategically engineered features. The Random Forest model achieves **79.75% accuracy (R² = 0.7975)** with a mean prediction error of **$44,059**.

## Key Results

| Metric | Value |
|--------|-------|
| **Algorithm** | Random Forest Regressor |
| **R² Score** | 0.7975 |
| **RMSE** | $44,059 |
| **Improvement vs Baseline** | 27.1% |
| **Dataset Size** | 19,648 samples |
| **Features Used** | 10 (8 original + 2 engineered) |

## Project Workflow

### 1. Data Preparation
- Loaded California Housing Dataset (20,640 samples)
- Detected and removed outliers using Interquartile Range (IQR) method
- Removed 992 extreme price outliers (4.8% of data)
- Verified data quality with minimal missing values

### 2. Exploratory Data Analysis
- Analyzed feature correlations with target variable
- Identified strong geographic relationships (Latitude/Longitude)
- Observed right-skewed price distribution indicating luxury properties
- Discovered median income as primary price driver

### 3. Feature Engineering
Created 3 targeted engineered features based on domain knowledge:

- **IncomePerOccupant** - Median income divided by average household occupancy (strongest predictor, 51.9% importance)
- **BedroomRatio** - Proportion of bedrooms to total rooms
- **RoomsPerBedroom** - Average rooms divided by average bedrooms (spaciousness metric)

These features capture non-linear relationships and domain-specific insights that raw features cannot represent.

### 4. Model Development
Compared two approaches:

**Baseline: Linear Regression**
- R² Score: 0.6274
- RMSE: $59,764

**Selected: Random Forest Regressor**
- R² Score: 0.7975 ✓
- RMSE: $44,059 ✓
- Parameters: 100 trees, max_depth=15

### 5. Model Evaluation
- Validated on held-out test set (20% of data)
- Analyzed feature importance rankings
- Confirmed no significant overfitting (train R²: 0.8956, test R²: 0.7975)

## Top 3 Feature Importance

1. **IncomePerOccupant (Engineered)** - 0.519 (51.9%)
2. **Longitude** - 0.144 (14.4%)
3. **Latitude** - 0.136 (13.6%)

These three features account for 79.9% of the model's predictive power. Note that the engineered feature (IncomePerOccupant) dramatically outperforms all raw features, demonstrating the value of domain-driven feature engineering.

## Technical Stack

- **Data Processing**: pandas, numpy
- **Machine Learning**: scikit-learn
- **Model Persistence**: joblib
- **Environment**: Python 3.12

## Model Performance Metrics

- **Training R² Score**: 0.8956
- **Test R² Score**: 0.7975
- **Training RMSE**: $34,521
- **Test RMSE**: $44,059

The model generalizes well with minimal overfitting, demonstrating robust learning on held-out data.

## Key Insights

1. **Strategic feature engineering is highly effective** - The engineered IncomePerOccupant feature is the single strongest price predictor at 51.9% importance, substantially outperforming all original features

2. **Geographic location matters** - Combined latitude and longitude importance is 27.6%, indicating location is second most important factor

3. **Ensemble methods excel** - Random Forest achieved 27.1% R² improvement over Linear Regression baseline

4. **Data quality improves results** - Removing extreme outliers reduced prediction error variance and improved model stability

## Methodology and Approach

### Feature Engineering Strategy
Rather than creating many features arbitrarily, this project focused on creating meaningful features based on:
- **Domain knowledge**: Income per person is economically meaningful
- **Problem intuition**: Bedroom proportion relates to property type
- **Statistical analysis**: Correlation analysis guided feature selection

### Model Selection Rationale
Random Forest was chosen over Linear Regression because:
- Can capture non-linear relationships between features and prices
- Handles feature interactions automatically
- Provides feature importance rankings for interpretability
- More robust to outliers and data variations

## Limitations and Future Work

- Model trained on California housing data; regional variations may affect generalization
- Price data is from 1990 census; does not reflect current market conditions
- Additional features (proximity to amenities, school quality, crime rates) could improve accuracy
- Time-series analysis could capture temporal market trends
- Hyperparameter tuning could further optimize performance

## Code Quality Standards

- Clean, well-documented code with descriptive variable names
- Proper separation of concerns (data loading, preprocessing, modeling, evaluation)
- Comprehensive docstrings for all functions
- Clear markdown sections explaining each analytical step
- Production-ready code following Python best practices

## Conclusion

This project demonstrates a practical end-to-end machine learning workflow: from exploratory analysis through feature engineering to model validation. The strategic creation of domain-informed features and ensemble learning approach resulted in a model that explains nearly 80% of house price variance with a mean prediction error of under $45,000.

---

**Project Status**: Complete and Validated ✓

**Author**: Tanzeel Ahmed  
**Year**: 2026
