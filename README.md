# Analysis and Prediction of the SOFC Parameters by Data-Driven Modeling

This repository contains the source materials and calculation results used in the study ***SOFC Voltage Prediction by Data-Driven Approach***

In this version:
- add Data Preprocessing
- add grade feature important (MDI, PI, SHAP, PCA)

Report:

**(!)squarederror**  *the most narrative features*
<br>top 3 high weights
- MDI:  0.965586, 0.009850, 0.007659
- PI:   0.593551, 0.058517, 0.054146
- SHAP: 15.56, 1.53, 1.33
- PCA:  0.892817, 0.031799, 0.029172

<br>top 10 strong feature
- MDI:  T21, T17, T5, T20, T16, T25, T9, T22, Q_CH_N2, pump_spd
- PI:   Т21, T17, T5, T20, T16, T3, T9, I, T19, W
- SHAP: Т21, Т17, Т5, Т20, Т16, Т3, Т9, I, Q_CH_N2, W  

general signs for PI and SHAP (9): **Т21, Т17, Т5, Т20, Т16, Т3, Т9, I, W** <br>

**squaredlogerror**
- MDI:  0.674076, 0.283172, 0.011238
- PI:   0.314902, 0.140141, 0.098361
- SHAP: 8.11, 5.51, 1.32
- PCA:  0.771667, 0.070112, 0.065652
<br>
- MDI:   T21, T17, T20, T16, T9, T30, Q_CH4, impl_spd1, impl_spd2, O2
- PI:    T21, T17, T20, T16, T9, T22, Q_CH4_N2, T25, T27, pump_spd
- SHAP:  T21, T17, T20, T16, T9, T22, Q_CH4_N2, T5, impl_spd1, pump_spd
 <br>
general signs for PI and SHAP (8): **T21, T17, T20, T16, T9, T22, Q_CH4_N2, pump_spd** <br>

<br>**pseudohubererror** 
- MDI:  0.228194, 0.126173, 0.095932
- PI:   3994.005569, 1944.821739, 1343.692211
- SHAP: –
- PCA:  0.410946, 0.251196, 0.156792
<br>
- MDI:  T20, T5, T21, T17, T19, T16, T23, T3, Q_CH4_N2, T27
- PI:   T20, T5, T21, T17, T19, T16, T23, T3, Q_CH4_N2, T27
- SHAP: –
 <br> general signs for PI and MDI 10/10, *but SHAP breaks* <br>

<br>**(!)absoluteerror**  *the best distribution of weights between features* <br>
- **MDI:  0.232931, 0.182060, 0.066103**
- **PI:   0.437368, 0.100107, 0.064641**
- **SHAP: 9.44, 5.72, 2.09**
- **PCA:  0.257019, 0.180864, 0.134216**
<br>
- MDI:  T17, T20, T5, T9, T21, T19, T16, T30, I, T27
- PI:   T17, T20, T5, T9, T21, T25, Q_CH4_N2, pump_spd, T3, T23
- SHAP: T17, T20, T5, T9, T21, T25, Q_CH4_N2, Q_CH4, pump_spd, T23

general signs for PI and SHAP (9): **T17, T20, T5, T9, T21, T25, Q_CH4_N2, pump_spd, T23**  <br>

**Total:**
- General strong features: T21, T17, T20, Q_CH4_N2 <br>
- General average features: T16, T5, T9, pump_spd <br>