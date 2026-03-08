# Median:

Median = The middle value of sorted data.

Steps:
1. Sort the data.
2. Pick the middle number

example : 10,20,30,40,50
Middle value : 30

if number of value is even , like => 10,20,30,40
then we took the average of middle values => (20+30) / 2 = 25

Median / middle value = 25


## Median Intution
Median Splits the data into two halves

Left side = 50%
Right side = 50%

## Why median is important:
Median is useful , if data contains outliers

=> 10, 20, 30, 40, 1000

Mean = 220 
Median = 30

Median is robust (strong) even there are outliers.

## Mathematical idea behind Median:

Mean minimize Squared Error (y - y_pred)^2.

likwise,

Median minimize Absolute error | y - y_pred |
Meidan is center of the point
points on left = points on right
So the balance point is the middle value , hence eror less , as its not squaing , this the right choice for ABsolute Error calculation.


## Median usage:
1. MAE Loss
2. Robust Regression
3. Quantile Regression.


