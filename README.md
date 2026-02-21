# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) drop combine similar feature in `SOFC_analisys.ipynb` (transition from 25 to 29 features)
2) switching to a new engine (CatBoost)
3) standardization has been replaced by normalization (MinMaxScaler)

### fit result

| model (components) | R2_score | MSE | MAE | MAPE | second |
| --- | --- | --- | --- | --- | --- |
| *Gradient Boosting* |
| **CatBoost_default(full)** | **0.99724** | **0.9087** | 0.238 | 2.78% | 2.682589 |
| CatBoost+PCA(5) | 0.99491 | 1.6733 | 0.380 | 5.04% | 5.343055 |
| CatBoost+SHAP(8) | 0.99485 | 1.6943 | 0.380 | 2.90% | 4.547544 |
| CatBoost+PI(8) | 0.99715 | 0.9389 | 0.267 | 2.24% | 4.190729 |
| CatBoost+MDI(13) | 0.99502 | 1.6373 | 0.345 | 2.75% | 4.654885 |
| *Random Forest* |
| **XGBRF_default(full)** | 0.99701 | 0.9835 | **0.261** | **1.10%** | 4.007105 |
| XGBRF+PCA(29) | 0.99607 | 1.2899 | 0.284 | 1.34% | 2.987392 |
| *MultiLayer Preceptron*|
| MLP_default(full) | 0.99154 | 2.7549 | 0.884 | 7.88% | 1.718075 |
| MLP+PCA(21) | 0.99567 | 1.4255 | 0.392 | 3.32% | 3.493348 |
				

**Conclusion**:
- full feature set with default **XGBRandom_Forest** model demonstrated the best results for *MAE*, *MAPE* metrics
- full feature set with default **CatBoost** model demonstrated the best results for *time*, *R2* and *MSE* metrics
- full feature set with default **MLP** model demonstrated the best results for *time* metrics
- MLP+PCA works even slower than the default MLP, although it gives a more accurate result