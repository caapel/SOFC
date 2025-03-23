# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) added MSE-metric on plot

### fit result

| model (components) | R2_score | MSE | MAE | MAPE | second |
| --- | --- | --- | --- | --- | --- |
| *Gradient Boosting* |
| **XGB_default(full)** | **0.99698** | **0.9940** | 0.309 | 2.63% | 0.172760 |
| XGB+PCA(19) | 0.99524 | 1.5670 | 0.392 | 3.52% | 0.142445 |
| XGB+SHAP(11) | 0.99660 | 1.1180 | 0.383 | 3.40% | 0.095001 |
| XGB+PI(11) | 0.99658 | 1.1234 | 0.384 | 3.40% | 0.093776 |
| XGB+MDI(10) | 0.99525	 | 1.5604 | 0.427 | 3.52% | 0.091928 |
| *Random Forest* |
| **XGBRF_default(full)** | 0.99680 | 1.0546 | **0.266** | **1.12%** | 3.215760 |
| XGBRF+PCA(13) | 0.99518 | 1.5818 | 0.336 | 1.55% | 2.389213 |
| *MultiLayer Preceptron*|
| MLP_default(full) | 0.99468 | 1.7546 | 0.554 | 5.89% | 2.444528 |
| MLP+PCA(23) | 0.99527 | 1.5553 | 0.490 | 4.82% | 2.148090 |
				

**Conclusion**:
- full feature set whis default **XGBRandom_Forest** option demonstrated best result for *MAPE* metric
- full feature set whis default **XGBoost** option demonstrated best result for *time*, *R2* and *MSE* metric
- reducing the dimensionality of components gives a negative result and therefore the tools (SHAP, PI, MDI) *do not make sense*
- MLP showed the worst result. MLP+PСA somewhat speed up the algorithm and increase accuracy, but do not improve the result globally