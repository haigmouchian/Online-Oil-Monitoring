# Online-Oil-Monitoring

In this project I am going to analyze how can we predict a very important property of lubricating oils: the Total Acid Number, or TAN. This variable is measured in mgKOH/g of fluid. The range of the experimental samples was from 0 to 4mgKOH/g, aproximately.

This property is a measure of the oil oxidation, which is finally a measure of its degradation level.

For this, I am going to use measurements of an oil sensor 'P' which senses electrical properties. There are also measurements of other 2 sensors, 'Y' and 'T' but in this notebook I am only going to focus on the 'P' sensor.

As I am trying to predict TAN, which is a numerical label, this is a regression problem.

The best base model was **XGBoost Regressor**, and I used this model for hyperparameter tuning and final evaluation. 

The obtained results were quite good. I used Root Mean Squared Error (RMSE) as my scoring benchmark and these were the final results:
* **Training RMSE:** 0.0025
* **Test RMSE:** 0.0783
In samples with TAN > 3 the model accuracy does start to decrease. Given our domain knowledge, this was expected. At very high degrees of oxidation (TAN>2.5) the oil starts changing at a molecular level, and its chemical properties change. Predictions become much harder to make, since other variables start to govern. However, the proposed model performs very well, specially with low to mid-high TAN values.

Finally, acknowledgements for the different sections:
* Modelling:
    - Several model evaluation: https://github.com/PlayingNumbers/ds_salary_proj
    - XGBoost Regression Model Hyperparameter Tuning: https://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/
