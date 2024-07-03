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

Model                     LinearReg     Seq_Linear   Lasso_Linear    Lasso_Ridge     Ridge_Grid
total_coeff                   22.00          11.00          21.00          21.00          21.00

condition                    627.27         641.64         627.27         627.27         627.27
fuel                       -2918.48       -2913.93       -2918.48       -2918.47       -2918.48
cylinders                  -1659.37       -1628.08       -1659.37       -1659.38       -1659.37
size                         332.27                        332.27         332.26         332.27
title_status               -1610.86       -1611.64       -1610.86       -1610.85       -1610.86
transmission                2174.25        2254.80        2174.25        2174.23        2174.25
drive                      -4645.89       -4639.43       -4645.89       -4645.85       -4645.88
paint_color_a_color          429.94        1031.33         922.14         916.93         921.62
paint_color_black            736.32        1303.68        1228.53        1223.30        1228.00
paint_color_blue            -693.16                       -200.95        -206.15        -201.48
paint_color_brown           -644.35                       -152.14        -157.31        -152.66
paint_color_custom          -670.31                       -178.11        -183.28        -178.63
paint_color_green            -24.67                        467.54         462.22         467.00
paint_color_grey           -1665.49                      -1173.28       -1178.43       -1173.80
paint_color_orange          -492.21                                                            
paint_color_purple         -1268.99                       -776.78        -780.05        -777.11
paint_color_red              273.82                        766.03         760.79         765.50
paint_color_silver          -629.52                       -137.32        -142.52        -137.84
paint_color_white           1407.09        1963.35        1899.30        1894.06        1898.77
paint_color_yellow          3241.51                       3733.71        3725.40        3732.88
year                        1657.03        1653.96        1657.03        1657.03        1657.03
odometer                      -0.01          -0.01          -0.01          -0.01          -0.01

intercept               -3300277.32    -3294564.98    -3300769.53    -3300763.25    -3300768.89

train_mse               88659680.42    88870536.32    88659680.42    88659680.59    88659680.42
test_mse                86261770.88    86428473.08    86261770.88    86261789.74    86261772.77
## Insights
Coupons 'Restaurant(<20)' and 'Carry out & Take away' have higher acceptance rate.
Drivers who already visited bar are likely to accept Bar coupons. Age above 30 is a factor. Also passanger being a kid also affecting decision to going to Bar.
Attributes like age, marital status, occupation does not seems much effect in accepting coupons.
