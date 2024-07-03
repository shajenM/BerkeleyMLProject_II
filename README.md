# Berkeley Machine Learning Course Application
## Project
This project was developed as part of my Berkeley Machine Learning course. Here dataset on car sales is analysed to predict price of car.

## Data Cleanup
The data set has 426880 entries and 18 features. Major features are: 
```
price
year
manufacturer
condition
cylinders
fuel
odometer
title_status
transmission
drive
size
type
paint_color
state
```
Most of the columns have missing values. There are 1,215,152 missing values in data. Some cars have price 0, which not make sense. So I used data with car prices from $1000 to $80,000. The sales information starts from year 1900. To make data more relevant, I used entries since year 2000.

Columns id and VIN are dropped, since they do not affect change in price. Region and State represent the same, so dropped Region.
'model' and size are similer, so dropped the model column.

#### Missing values were replaced with a value as below.
```
manufacturer: "a_company"
condition   : "good" 
cylinders   : "4 cylinders"
size        : "mid-size"
odometer    : 50000.0
fuel        : "gas"
title_status: "missing"
transmission: "other"
drive       : "rwd"
type        : "other"
paint_color : "a_color"
```
## Data analysis
Most of the data are catagorical in nature. To start with, the histogram shows the sales and their price range. Most of the cars sold are in price between 100 to 40,000.

![PriceRange](histPrice.png)


The year and odometer are only numerical features in dataset. Thier relation with price is analyzed below:
![HeatMap](car_heatmap.png)


The line plot on year vs price suggest that cars from recent years have higher price.
![YearPrice](year_price.png)


The scatter plot on odometer shows its lack of relationship on price.
![OdometerPrice](odometer_price.png)


The new and good condition cars have more sales. The boxplot below suggests that.
![ConditionPrice](condition_price.png)


Cars with clean title have more sales.

![TitlePrice](title_price.png)


The Four Wheel and Rear Wheel drives have higher sales.
![DrivePrice](drive_price.png)

Some interesting information were found from data. For example, California has high car sales. Cheverlot and Ford Manufacturers have sold most of cars. Toyota is on third place.
![States](sales_state.png)
![manufactures](sales_manufacturer.png)

# Model Training
 For traininig and test purpose data is splited with 20% for testing.
 The categorical features are ordinal categories. They are encoded using OrdinalEncoder.  Car color is encoded with OneHotEncoder.

 Following models were explored.

### Model: Basic Linear Regression.

This model has coefficients of year, condition, size, transmission, yellow color and white color makes car price high.
Title, fuel, number of cylinder and grey color affects car price negatively.
Odomoter is not affected the price. 

The model has prediction error:
Train MSE:  88659680.42
Test  MSE:  86261770.88

### Model: Linear Regression with Sequential Feature Selection
The Sequential Feature selector helped to reduce number of features to 11.
Not sure why odometer is selected even though it has less effect on price.

The error on prediction remain close to basic linear regression model.

### Model: Linear Regression with Lasso Based Feature Selection
The lasso selected all features except color orange
The prediction error remain almost same

### Model: Ridge Regression with Lasso Based Feature Selection
In this model Ridge regression is used and Lasss for feature selection. It selected all the features except Orange car color.
The error in prediction remain same as basic linear regression.
The alpha value is 1.0

### Model: GridSearch and Cross validation on Rdige Regression
This model is built using GridSearch and Cross Validation of 5 times. Lasso is the estimator for paramters. Ridge is used for regression.
The grid search determined aplha value 1.0. 
In terms of gain, not much different from basic linear regression

### Comparison Report

Here is the report on comparison of parameter values and prediction error of all 5 models.

![Test model](ModelReport.png)

## Conclusion
#### Model with lowest prediction error is Lasso with Linear Regression. But this took higher amount of time to trian
#### Sequential Feature selector helped to reduce number of features, but did not helped to reduce prediction error.

##### Odomerter has less effect on price. Not sure Sequential selector and Lasso did not remove Odometer column
##### I found basic Linear Regression is best model among these since it takes less time to train and error is almost same as others
##### In this model
#####    White and yellow color, Condition of car, size, trasmission and year affects price to increase.
#####
