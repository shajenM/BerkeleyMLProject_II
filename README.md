# Berkeley Machine Learning Course Application
## Project
This project was developed as part of my Berkeley Machine Learning course. Here dataset on car sales is analysed to predict price of car.

## Data Cleanup
The Car column has many missing data. Since the type of car does affect drivers decision to accept coupon, missing values are  replaced with value 'unknown'.
The columns Bar, CoffeeHouse, CarryAway, RestaurantLessThan20 and Restaurant20To50 also have missing values. These are also decided to replace with value 'unknown'
since it will not affect much.

## Data analysis
Most of the data are catagorical in nature. So barcharts and histograms are used for analisys.

## Insights
Coupons 'Restaurant(<20)' and 'Carry out & Take away' have higher acceptance rate.
Drivers who already visited bar are likely to accept Bar coupons. Age above 30 is a factor. Also passanger being a kid also affecting decision to going to Bar.
Attributes like age, marital status, occupation does not seems much effect in accepting coupons.
