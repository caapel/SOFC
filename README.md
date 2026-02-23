# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) drop combine similar feature in `SOFC_analisys.ipynb` (transition from 25 to 29 features)
2) switching to a new engine (CatBoost)
3) standardization has been replaced by normalization (MinMaxScaler)
4) added SHAP force & dependency plot for XGBRandom_Forest

### fit result

| model (components) | R2_score | MSE | MAE | MAPE | second |
| --- | --- | --- | --- | --- | --- |
| *Gradient Boosting* |
| **CatBoost_default(full)** | **0.99724** | **0.9087** | 0.2384 | 2.78% | 2.564952 |
| CatBoost+PCA(11) | 0.99554 | 1.4657 | 0.3435 | 4.75% | 2.301819 |
| CatBoost+SHAP(10) | 0.99514 | 1.5969 | 0.3509 | 2.50% | 2.047301 |
| CatBoost+PI(8) | 0.99732 | 0.8826 | 0.2588 | 2.12% | 2.011584 |
| CatBoost+MDI(13) | 0.9969 | 1.016 | 0.2455 | 2.60% | 2.298787 |
| *Random Forest* |
| **XGBRF_default(full)** | 0.99701 | 0.9835 | 0.2606 | **1.10%** | 3.821726 |
| XGBRF+PCA(29) | 0.99607 | 1.2899 | 0.284 | 1.34% | 3.170665 |
| XGBRF+SHAP(15) | 0.99696 | 1.0014 | 0.249 | 1.12% | 1.720645 |
| XGBRF+PI(15) | 0.99668 | 1.0934 | **0.242** | 1.18% | 1.798448 |
| XGBRF+MDI(12) | 0.99501 | 1.6398 | 0.328 | 1.28% | **1.547774** |
| *MultiLayer Preceptron*|
| MLP_default(full) | 0.99154 | 2.7549 | 0.884 | 7.88% | 1.783327 |
| MLP+PCA(21) | 0.99567 | 1.4255 | 0.392 | 3.32% | 3.726366 |
| MLP+PI(13) | 0.98884 | 3.6077 | 0.978 | 8.80% | 1.588605 |
				

**Conclusion**:
- full feature set with default **XGBRandom_Forest** model demonstrated the best results for *MAE*, *MAPE* metrics
- full feature set with default **CatBoost** model demonstrated the best results for *time*, *R2* and *MSE* metrics
- full feature set with default **MLP** model demonstrated the best results for *time* metrics
- MLP+PCA works even slower than the default MLP, although it gives a more accurate result