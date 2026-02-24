# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) drop combine similar feature in `SOFC_analisys.ipynb` (transition from 25 to 29 features)
2) switching to a new engine (CatBoost)
3) standardization has been replaced by normalization (MinMaxScaler)
4) added SHAP force & dependency plot for XGBRandom_Forest
5) scale selection between MLP & DTs (GB & RF)

### fit result

| model (components) | R2_score | MSE | MAE | MAPE | second |
| --- | --- | --- | --- | --- | --- |
| *Gradient Boosting* |
| CatBoost_default(full) | 0.99725 | 0.9069 | 0.238 | 2.78% | 2.571273 |
| CatBoost+PCA(11) | 0.99555 | 1.4629 | 0.346 | 4.93% | 2.184407 |
| CatBoost+SHAP(8) | 0.99489 | 1.6808 | 0.379 | 2.89% | 1.937381 |
| **CatBoost+PI(10)** | **0.99732** | **0.8843** | 0.259 | 2.12% | 1.929342 |
| CatBoost+MDI(14) | 0.99692 | 1.0168 | 0.246 | 2.60% | 2.189198 |
| *Random Forest* |
| **XGBRF_default(full)** | 0.99701 | 0.9835 | 0.261 | **1.10%** | 3.643324 |
| XGBRF+PCA(29) | 0.99607 | 1.2899 | 0.284 | 1.34% | 2.862980 |
| XGBRF+SHAP(15) | 0.99696 | 1.0014 | 0.249 | 1.12% | 1.651798 |
| XGBRF+PI(15) | 0.99668 | 1.0934 | **0.242** | 1.18% | 1.725580 |
| XGBRF+MDI(12) | 0.99501 | 1.6398 | 0.328 | 1.28% | **1.493196** |
| *MultiLayer Preceptron*|
| MLP_default(full) | 0.99154 | 2.7549 | 0.884 | 7.88% | 1.854000 |
| MLP+PCA(21) | 0.99567 | 1.4255 | 0.392 | 3.32% | 3.657471 |
| MLP+PI(13) | 0.98884 | 3.6077 | 0.978 | 8.80% | 1.639187 |
				

**Conclusion**:
- full feature set with default **XGBRandom_Forest** model demonstrated the best results for *MAE*, *MAPE* metrics
- full feature set with default **CatBoost** model demonstrated the best results for *time*, *R2* and *MSE* metrics
- full feature set with default **MLP** model demonstrated the best results for *time* metrics
- MLP+PCA works even slower than the default MLP, although it gives a more accurate result