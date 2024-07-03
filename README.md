# Berkeley Machine Learning Course Application
## Project
This project was developed as part of my Berkeley Machine Learning course. Here dataset on car sales is analysed to predict price of car.

## Data Cleanup
The data set has 426880 entries and 18 features. Major columns are: 
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

Most of the column have missing values.
Some cars have price 0, which not make sense. So I car prices from 1000 to 80,000.
The data is since year 1900 which may not be relevent now. I used data from year 2000.

Drop columns id and VIN, since they do not represent change in price
Drop region, same as state
Model and size are similer, so dropped column model

### Replace missing values for columns as below.
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

## Data analysis
Most of the data are catagorical in nature. So barcharts and histograms are used for analisys.
![Test Image 1](car_heatmap.png)
# Model Training
 Split data for traininig and test with 20% for testing
 These categories are ordinal categories. They are encoded using OrdinalEncoder
  Car color is encoded with OneHotEncoder

### MODEL 1
    Basic Linear Regression model

### MODEL 2
    Basic Linear Regression model
### MODEL 3
    Basic Linear Regression model
### MODEL 4
    Basic Linear Regression model
### MODEL 
    Basic Linear Regression model

![Test model](ModelReport.png)

## Insights
Coupons 'Restaurant(<20)' and 'Carry out & Take away' have higher acceptance rate.
Drivers who already visited bar are likely to accept Bar coupons. Age above 30 is a factor. Also passanger being a kid also affecting decision to going to Bar.
Attributes like age, marital status, occupation does not seems much effect in accepting coupons.
