# Featrue Scaling:
 Feature Scaling is the process of standardizing / normalizing the range of independent features in dataset, it brings all data into a 
 similar scale , so that no single dataset  dominates others because of its magnitude.

 Examlple :  Age 20-80 , Balance = 20000 - 100000.
 Without Scaling model might consider more in Balance due to higher magnitude.


 ### Why needed:
     1. Improves Model Performance.
     2. Required for distance based models.
     3. Prevents numerical instabiltiy.
     4. Help Regularaization.
     5. Increased speed of convergence.

## Types of Feature Scaling:

### 1. Min - Max Scaling ( Normalization ) / ( Unit Scaling ) :
    Scales features to fixed range [ 0 to 1 ] 
    Formulae =   x - xmin 
               -------------
                xmax - xmin
    x = original value
    xmax - maximum value of the feature.
    xmin - minimum value of the feature.

    When To use:
    ------------
    1. When we know the min and max and want a bounded range.
    2. Sensitive to outliers , it shrinks the normal data also.

### 2. Standardization (z- score Scaling ):
    1. Scales features to have mean = 0 and standard deviation = 1
    Formulae =       x - mean
                  ---------------
                        std

    x - original value / current value.
    mean - mean of features.
    std - Standad dviation of features.

    When to use:
    -------------
    1. When we have outliers.

### 3. Max Absolute Scaling:
    1. Scales features to -1 to 1 by diving the  maximum absolute value of the feature.
    Formulae =     x / |xmax|

    When to use:
    -----------
    1. Data is already centered at zero.
    2. Does not shift /center data ( unlike standardization ) 

### 4. Robust Scaling:
    1. Uses median and IQR instead of mean and std , useful for outliers

    Formulae =    x - median
                -------------
                     IQR

    x = Original Data
    median = Center of the data.
    IQR = InterQuartile Range ( Q3 - Q1 ) ( 75th percentile - 25 th percentile ) 

    When to use:
    -------------
    Dataset has outliers , thats are valid 
    Does not Squash the normal data like standaradization due to outliers.

### Unit Vector Scaling ( Normalization by Vecotr Length):
    1. Its a row wise Scaling
    2. Trear each row as a vector 
    3. Idea is to scale the vector so its length would be equal to  1. 

    formulae =      X
                ---------
                  ||X||


    








    
