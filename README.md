
# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
1) remove 18324 lines with zero target feature from general set
2) add 7 variant XGboost Regressor:
+ squarederror (sqr)
+ squaredlogerror (sqrlog)
+ pseudohubererror (pseudo)
+ absoluteerror (abs)
+ PCA (absoluteerror, 5 component)
+ PCA (squarederror, 6 component)
+ full feature set whis default XGBoost option (default)

### fit result
| model | sqr |  sqrlog | pseudo | abs | PCA-abs(5) | PCA-sqr(5) | default |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R2_score| 0.996087 | 0.978029 | 0.976664 | 0.987903 | 0.990631 | 0.994815 | 0.997026 |
| MSE | 1.285899 | 7.053912 | 7.692904 | 3.943018 | 3.055593 | 1.704469 | 0.979206 |
| MAE | 0.451797 | 1.404085 | 1.277448 | 0.815767 | 0.629195 | 0.440888 | 0.309010 |
| MAPE | 4.07% | 5.25% | 9.29% | 6.93% | 9.73% | 4.40% | 2.82% |

**Conclusion**:
- MSE metric is not applicable in the context of this study
- full feature set whis default XGBoost option demonstrated best result
- absoluteerror & pseudohubererror – bad learning objective
- squarederror – good learning objective