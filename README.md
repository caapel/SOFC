# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) added time measurement for scripts
2) added dataframe `df_search_result` with results of model training (section 4: Result)

### fit result

| model | R2_score | MSE | MAE | MAPE | second |
| --- | --- | --- | --- | --- | --- |
| XGB default | 0.99698 | 0.9940 | 0.309 | **2.63%** | 0.179379 |
| XGB+PCA | 0.99476 | 1.7219 | 0.411 | 3.94% | 0.126611 |
| XGB+SHAP | 0.99660 | 1.1180 | 0.383 | 3.40% | 0.116858 |
| XGB+PI | 0.99658 | 1.1234 | 0.384 | 3.40% | 0.117702 |
| XGB+MDI | 0.99564	 | 1.4293 | 0.410 | 3.54% | 0.113655 |


**Conclusion**:
- MSE metric is not applicable in the context of this study
- full feature set whis default XGBoost option demonstrated best result
- reducing the dimensionality of components gives a negative result and therefore the tools (SHAP, PI, MDI, PCA) *do not make sense*