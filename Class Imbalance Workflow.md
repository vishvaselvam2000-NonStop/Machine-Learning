# Class Imbalance

If target classes have vast differneces then thats class imbalance
for example , for Cancer dataset

Not Cancer --> 90%
Cancer --> 10%

Here Non cancer pstients are more in number , will then they dominate the flow , and model learns majorly that leads to predict always non 
cancer even if they are cancer patient,which is very might risk and invalid

## Handling Class Imbalances:

* Data Level techniques
* Algorithmic Level techniques
* Ensemble Technique
* Evaluation Tricks

## 1. Oversampling ( Increasing Minority Classes)
     * Randomly Duplicate samples from the minority classes.
     * Popular method is SMOTE ( Synthetic Minority Oversampling Technique )
### SMOTE:
     * SMOTE idea is the insteady of copying / duplicating samples at random , create synthetic samples along the line segments
     * Connecting minority class points
  ### SMOTE Working:
     * Pick a minority class sample xi.
     * Find K nearest neighbours of xi , ex , k = 5 , 5 nearest number will get chose.
     * Randomly select one of 5 nearest neighbour.
     * Generate a Synthetic samples by Interpolation
     xnew = xi + & .( xzi (new point - xi)

     So the new point is not a random point its a point which are lies in feature space.
  ### Key points of SMOTE:
      1. Works For continous features ( numerical )
      2. Avoid overfitting comapred to random oversampling.
      
    

