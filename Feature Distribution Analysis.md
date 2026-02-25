# Feature Distribution Analysis.
To Study how the values of each feature are spread / Disributed.

## Numerical Feature Analysis: 

* Values are Concentrated in middle
* Skewed?
* Multiple peaks?

### We check using:
1. Histogram
2. Boxplot
3. Skew Values

## 1.Histogram:
How values of a feature are distributed?
* Where most value are  lies
* Are values spread out?
* Skewness
* Multiple peaks?

### How Histogram built:

    Example:
    ages = 21, 22, 23, 24, 25, 35, 37, 40, 46, 50.
    Divide values into groups called **Bins**
    Example BINS : 20-30 , 30-40, 40-50 ( 3 BINS )
    Count how many values fall in each BINS , that count is the BAR height.

### SHAPES OF HISTOGRAM:
    1. Normal (BELL SHAPE):
       * Most values are lies in center
       * few on left and few on right
       * Skew = 0
       Very Balanced distribution

    2. Right Skewed (  Positive Skew) 
       * Most Values are small
       * Few Data Very large
       * Tail goes to right
       * Mean > Median
       * Skew >  0

    3. Left Skewed ( Negative Skew )
       * Most Values are Large
       * Few Smaller values
       * Tail goes to left
       * Skew < 0

    4. Uniform Distribution ( Flat ):
       * Values Evenly spread across overall
       * No central Peak
       * Skew =0 ( approximatley more or less )
       * Not bell  shaped.

### Histogram Vs Bar Chart:
    Histogram:
    * Used for numeric continuous data
    * Bars touch each other
    
    Bar chart:
    Used for categorical data
    Bars separated

### Histogram Does not tell:
    * Correlation
    * Causation
    * Feature Importance.

### Final Cheetsheet:
| Shape | Description | 
|-------| ------------|
| Bell  | Valid / Good|
| Slightly Skew | Its Okay not problem|
| Heavy Skew | Consider Transformation |
| Extreme Tail / skew | Check outliers |
| Flat | Uniform |
| Multiple Peaks | Might represent Different groups | 


## 2. Box Plot:

* Distribution Spread
* Median
* Outliers
* Skew Direction

### Definition:
    A Box plot summarize using five numbers:
    1. Minimum whisler point
    2. Q1      ( 25th Percentile)
    3. Median  ( 50th Percentile)
    4. Q3      ( 75th Percentile)
    5. Maximum whisker point

    ___________  Maximum Whisker point
       |
       |
       |
       |
    ______      Q3     
    |      |
    | ---- |    Median  
    |      |
     ______     Q1
       |
       |
       |
    __________ Minimum Whisker point

  ### The Box ( Center ):
  * Q1 to Q3
  * IQR ( Inter Quartile Range ) = Q3-Q1
  * Contain 50% of the Data.

  ### Line Inside Box:
  * Median
  * Tells where the center of the data.

  ### The Whiskers:
  * Line extending from the point , its in minimum and also in maximum
  * Lower whisker point  = Q1 - 1.5 * IQR
  * Upper whisker point  = Q3 + 1.5 * IQR

  ### Outliers:
  * Anything above / below whisker point is called outliers, that are exteme values of the dataset.
  * Values far from  the normal range.

  ### Use of the Box plot:
  * Detect Outliers Quickly
  * Detect Skew , Median Closer to bottom -> right skew , Median  Closer to upper -> Left skew.


  ## 3. Skew:
   * Skew Tells Asymmentry of distribution
   * Tells which side tail is longer.
   * How Strong that tail is
   *  Skew Formulae: E[(X - mean)^3] \ Standar deviation ^3.
   *  Skew > 0 --> Positive Skew ( Right Skew )
   *  Skew < 0 --> Negative Skew ( Left Skew )

     | Skew Value        | Meaning           | Action        |
     |-------------------|-------------------|---------------|
     | -0.5 to +0.5      | Almost symmetric  | Leave it      |
     | 0.5 to 1          | Moderate skew     | Usually OK    |
     | > 1               | High skew         | Investigate   |
     | < -1              | High left skew    | Investigate   |

 ## Final Feature Distribtuion Workflow.
     1. Look Histogram ( shape ? Tail Direction? )
     2. Box Plot ( Outliers? Meidan Position ? )
     3. Skew ( Confirm Skew Strength ? Confirm Direction ? )


## Categorical Feature Analysis:
    * Count Categories
    * Check Imbalance
    * Detect rare Categories
    * Check Relationship with Target
    * Decide Encoding Method
    * Decide Keep / Drop 

### 1. Count Categories:
    * df ['column'].value_counts()
    * Tells Unique categories
    * Tells how many rows are in each category.
    * If one has ver low row column then model will overift, as its like try to memorize the pattern.
    
### 2. Percentage Distribution ( Category class imbalance)
    * Check how the percentage distributed among their categories.
    * df['column'].value_counts(normalize = True)
    * If one cateogry is less percentage model might ignore that.

### 3. Bar Plot:
    * Visual Undertanding is more easy.
    * Immediately it will help us to see the imbalance.

### 4. Check Rare categories:
    * If its only have few rows , its rare.
    * Mostly model might ignore it.
    * Create noise in the model

### 5. Relationship with target:
    * Using Crosstab
    * pd.crosstab(df['columns'], df['target'], normalize = ' index')

### 6. Encoding Design:
    *  A) Nominal Categories ( No Order ) --> use One hot Encoding.
    *  B) Ordinal Categories ( Preserve Order ) --> Label encoding.
    

  






 
