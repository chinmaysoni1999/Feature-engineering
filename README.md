The features engineering which is been done is pretty much :

Imputing missing values by proceeding sequentially through the data

Transforming some numerical variables that seem really categorical

Label Encoding some categorical variables that may contain information in their ordering set

Box Cox Transformation of skewed features (instead of log-transformation) : This gave me a slightly better result both on leaderboard and cross-validation.

Getting dummy variables for categorical features.

Then we choose many base models (mostly sklearn based models + sklearn API of DMLC's XGBoost and Microsoft's LightGBM), cross-validate them on the data before stacking/ensembling them. The key here is to make the (linear) models robust to outliers. This improved the result both on LB and cross-validation.

