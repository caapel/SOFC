# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) added searcher number of components for PCA
2) added 5 variant XGboost Regressor:
+ full feature set whis default XGBoost option (default)
+ XGBoost+PCA
+ XGBoost+SHAP
+ XGBoost+PI
+ XGBoost+MDI

### fit result
| model | default |  PCA | SHAP | PI | MDI |
| --- | --- | --- | --- | --- | --- |
| R2_score | 0.997 | 0.9948 | 0.9966 | 0.9966 | 0.9956 |
| MSE | 0.994 | 1.722 | 1.118 | 1.123 | 1.429 |
| MAE | 0.3086 | 0.4112 | 0.3834 | 0.3841 | 0.4099 |
| MAPE | **2.63%** | 3.94% | 3.40% | 3.40% | 3.54% |

**Conclusion**:
- MSE metric is not applicable in the context of this study
- full feature set whis default XGBoost option demonstrated best result
- reducing the dimensionality of components gives a negative result and therefore the tools (SHAP, PI, MDI, PCA) *do not make sense*