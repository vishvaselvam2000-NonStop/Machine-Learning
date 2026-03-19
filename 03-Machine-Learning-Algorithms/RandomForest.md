# Random Forest:

- Random Forest is an ensemble learning algorithm
- It combines multiple Decision Trees
- Uses Bagging (Bootstrap + Aggregation)

## 1. Core Concepts:

Bagging ( Bootstrap + Aggregation )
#### Bootstrap:

- Random samples from dataset
- With replacement
- Same data point can appear multiple times
- If we Bootstrap the Row data then its row sampling , and if we done on Columns is called Feature Sampling, RandomForest using both Sampling.

#### Aggregation:
 - Using and Combining the multiple the model outputs and with that we are making final decision.
 - Classification → Mode (majority vote)
 - Regression → Mean (average) / Median (Custom)

## 2. Randomness in RandomForest:

RandomForest adds Randomness in two ways:

#### 1. Row Sampling:
      Each tree gets new data , same size , but it might repeat the same data and also it might leave some data completely 
      Example:
      Dataset : have 10 rows , ex -> 1,2,3,4,5,6,7,8,9,10
      Tree1: 1,2,2,3,4,2,5,6,6,9 [ 2,6 - repeated , 7,8,10 are not there , not selected ] this the row sampling
      the left out values of tree1 -> 7,8,10 are out of bAG VALUES.

#### 2. Feature Sampling:
      At every split , a small subset of feature is considered, else it will ignore.
      This makes  trees less correlated.

## 3. Training Process:

  1. Take Dataset.
  2. Create multiple Bootstrap Samples.
  3. For each samples ,
     3.1 Train a Decision Tree.
     3.2 At each Split , choose random subset of features.
  4. Build many trees
  5. Store all models

## 4. Prediction:
   1. Input the new data.
   2. Pass through all the trees.
   3. Output:
      Classification -> Mode / MAjority Vote.
      Regression     -> Average   output.


## 5. OOB (Out of Bag ) Error:


      
