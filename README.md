# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) drop combine similar feature in `SOFC_analisys.ipynb` (transition from 25 to 29 features)

### fit result

| model (components) | R2_score | MSE | MAE | MAPE | second |
| --- | --- | --- | --- | --- | --- |
| *Gradient Boosting* |
| **XGB_default(full)** | **0.99707** | **0.9646** | 0.306 | 2.83% | 0.189227 |
| XGB+PCA(7) | 0.99492 | 1.6698 | 0.429 | 3.63% | 0.151798 |
| XGB+SHAP(11) | 0.99647 | 1.1602 | 0.360 | 3.38% | 0.093884 |
| XGB+PI(11) | 0.99648 | 1.1587 | 0.359 | 3.38% | 0.093288 |
| XGB+MDI(11) | 0.99555 | 1.4623 | 0.406 | 3.61% | 0.091611 |
| *Random Forest* |
| **XGBRF_default(full)** | 0.99701 | 0.9835 | **0.261** | **1.10%** | 3.690712 |
| XGBRF+PCA(21) | 0.99593 | 1.3383 | 0.315 | 1.45% | 2.564883 |
| *MultiLayer Preceptron*|
| MLP_default(full) | 0.99295 | 2.2964 | 0.799 | 8.73% | 2.077358 |
| MLP+PCA(21) | 0.99634 | 1.2032 | 0.381 | 4.23% | 2.109777 |
				

**Conclusion**:
- full feature set with default **XGBRandom_Forest** model demonstrated the best results for *MAE*, *MAPE* metrics
- full feature set with default **XGBoost** model demonstrated the best results for *time*, *R2* and *MSE* metrics
- Reducing the dimensionality of input feature vectors leads to an increase in error and therefore the SHAP, PI, MDI tools are useless
- MLP+PCA works even slower than the default MLP, although it gives a more accurate result