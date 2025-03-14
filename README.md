# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
add 5 variant XGboost Regressor:
+ the most narrative features (squarederror)
+ the best distribution of weights between features (absoluteerror)
+ PCA (absoluteerror, 7 component)
+ PCA (squarederror, 6 component)
+ full feature set whis default XGBoost option

### fit result
| model | sqr | abs | PCA-abs(7) | PCA-sqr(6) | default |
| --- | --- | --- | --- | --- | --- |
| R2_score| 0.999266 | 0.576463 | 0.583643 | 0.998599 | **0.999573** |
| MSE | 0.354625 | 90.595095 | 89.604189 | 0.677749 | **0.206910** |
| MAE | 0.187275 | 5.255869 | 5.293651 | 0.2169799 | **0.127325** |
| MAPE | 82.24% | 2.0e+14% | 2.0e+14% | 73.38% | **71.38%** |

**Conclusion**:
- MAPE metric is not applicable in the context of this study
- full feature set whis default XGBoost option demonstrated best result
- absoluteerror – bad learning objective
- to improve accuracy, you should delete rows with empty values ​​of the target feature "V"