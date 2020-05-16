# Project 2 - Ames Housing Data and Kaggle Challenge

**Problem Statement**
To create a regression model which predicts the sale price of a house. <br>
The model will help to identify various features of a house which can impact the price. <br>
The success of the model will be evaluated on how accurate the predictions are. <br>


-----

**Datasets**
This model is based on the Ames Housing Dataset. Two different datasets are used.
The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses.

- train.csv('./datasets/train.csv')
_This dataset is used for training and fine tuning the model._

- test.csv('./datasets/test.csv')
_This dataset is used for training and fine tuning the model._

Features for these datasets: Source: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

-----

**Data Cleaning and EDA**
- Checked and corrected the data types of each variable.
- Checked for null values.
- Data imputing was done based on the dataset documentation. <br>
Source: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt <br>
-  During EDA, outliers were identified using descriptive statistics, box plots and corrected accordingly.  <br>
- I used various plots like, box plot, scatter plot, histograms to visually explore the data for distributions.

**Preprocessing and Modeling**
The ordinal columns were mapped with numeric values.<br>
The categorical columns were converted to dummies (one-hot encoding). <br>
The data was splitted into train and test by train-test-split method. <br>
After train-split, training and testing data (only predictors) were scaled. <br>
The 4 models were used by me to analyse which performs better for given data:
- Linear regression
- Lasso
- Ridge
- ElasticNet
Out of these, Lasso performed best.<br>
Therefore, i selected lasso model for training the model and predicting sale price.


**Evaluation and Conceptual Understanding**
Cross_val_score(R2 score) was used to evaluate model's performance.
Residual plots also helped to understand the residuals distribution and their relationship with predictor variables.

**Conclusion and Recommendations**
Below are the features (alongwith with how impactful they are) that add most value to a home. 
These all have positive impact on value of a house. Therefore, higher the features, higher the value.

|Feature|coefficients|Description|
|:---|:---:|:---|
|gr_liv_area|24936.46|Above grade (ground) living area square feet|
|overall_qual|10492.96|The overall material and finish of the house|
|total_bsmt_sf|8746.06|Total square feet of basement area|
|mas_vnr_area|6626.93|Masonry veneer area in square feet|
|neighborhood_NridgHt|6314.43|If the neighborhood is NridgHt|
|year_built|6243.16|Original construction date|
|garage_area|6073.93|Size of garage in square feet|
|exter_qual|5604.66|The quality of the material on the exterior|
|lot_area|5513.68|Lot size in square feet|
|neighborhood_StoneBr|5346.67|If the neighborhood is StoneBr|

--------

Below are the features (alongwith with how impactful they are) that decrease the value of a home. 

|Feature|coefficients|Description|
|:---|:---:|:---|
|ms_subclass|-3057.85|Type of dwelling involved in the sale|
|bldg_type_TwnhsE|-2798.17|If the Type of dwelling is TwnhsE: Townhouse End Unit|
|mas_vnr_type_BrkFace|-2389.47|If Masonry veneer type is BrkFace(Brick Face)|
|roof_style_Mansard|-1698.01|If roof style is Mansard|
|bedroom_abvgr|-1600.55|If Bedrooms are not above grade|
|bldg_type_Twnhs|-1498.21|If the Type of dwelling is Townhouse Inside Unit|
|kitchen_abvgr|-1441.67|If Kitchens are not above grade|
|neighborhood_NAmes|-1404.43|If neighborhood is Northwest Ames|
|bsmt_cond|-1379.73|general condition of the basement|
|neighborhood_SawyerW|-1150.55|If neighborhood is Sawyer West|

---------

Below are few things that homeowners can do to improve the home value:
- Remodeling of home for kitchen and bathrooms particularly.
- Improving the quality of material of home.
- Improving the landscape of a home (adding some plants/trees) or add square foot, if possible.
- De-clutter as much as possible.

---------

From the model, we can see that below neighborhoods have the most positive impact on a home. Therefore, These neighborhoods seem like they might be a good investment.

- neighborhood_NridgHt --  Northridge Heights
- neighborhood_StoneBr --  Stone Brook
- neighborhood_GrnHill --  Green Hills
- neighborhood_NoRidge --  Northridge
- neighborhood_Crawfor --  Crawford

---------

People's choice of features when they buy a house are different in different cities. For eg: in 1 city people might prefer to live in condominiums, while in other they may prefer standalone houses.
Plus the home features also can be different for different cities. Therefore, it is difficult to say whether the model will generalize well to other cities.

However, with more data we can always modify our model to suit the city's needs, thus, increasing its accuracy in predicting prices.

---------------

NOTE: The predictions were uploaded on Kaggle(https://www.kaggle.com/) under [Regression Challenge Sign Up](https://www.kaggle.com/t/cf68f4a276f44b59a3c6c843dbf9ed1e).

Kaggle score:
![](Images/Project2_kaggle_score.png)

