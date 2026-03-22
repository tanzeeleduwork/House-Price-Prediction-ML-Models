# House Price Prediction Model - Results

## Project Summary
Developed an ML model to predict house prices using advanced feature engineering and ensemble learning techniques.

## Model Performance

| Model | R² Score | RMSE |
|-------|----------|------|
| **Random Forest** | **0.7975** | **$44,059** |
| Linear Regression | 0.6274 | $59,764 |
| **Improvement** | **27.1% better R²** | **26.3% lower error** |

## Key Results

- **Training Samples**: 19,648
- **Features Engineered**: 10 features
- **Train/Test Split**: 80% / 20%
- **Best Predictor**: Income Per Occupant (0.519 importance)

## Model Insights

### Feature Importance
![Feature Importance](results/feature_importance.png)

### Price Distribution & Model Fit
![Model Comparison](results/model_comparison.png)

### Feature Correlations
![Correlation Heatmap](results/correlation_heatmap.png)

## What This Shows

**Model effectively captures 79.75% of price variance**
**27% improvement over baseline linear regression**
**Top 3 features identified and validated**
**Robust generalization on held-out test data**

---

*For detailed methodology and code implementation, see the project documentation.*
