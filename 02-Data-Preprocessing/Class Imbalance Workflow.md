# Class Imbalance

If target classes Numbers have vast differneces  then thats class imbalance
for example , for Cancer dataset

Not Cancer --> 90%
Cancer --> 10%

Here Non cancer patients are more in number , will then they dominate the flow , and model learns majorly that leads to  have higher chance that model will more predict non cancer even if they are cancer patient,which is very might risk and invalid.

## Handling Class Imbalances:

* Data Level techniques.
* Algorithmic Level techniques.
* Hybrid Methods
* Evaluation level fix.


## 1. Data Level techniques:

### 1.1 Random OverSampling ( ROS ):
       In this technique we randomly duplicate the minority samples,  until we reach the equal to maximum sample size.

       Advantage:
       1. Simple
       2. No data loss
       3. Work well for small dataset.

       Disadvantage:
       1. Overfitting risk ( model will memory the pattern ) 
       2. Descision boundary does not imporve ( no new data creation )

       When we can use:
       1. Dataset is small
       2. Minority samples are very few.
       3. Quick method
       
 ### 1.2 Random Undersampling ( RUS ):
      Randomly remove data from the majority classes to balance the dataset with the minority.

      Disadvantage:
      1. Information loss
      2. Increased bias
      3. Higher variance

      Advantage:
      1. When majority is domininat extremely like 99%.

### 1.3 SMOTE ( Syntethic Minority Oversampling Technique ) :
    To solve problem of random Oversampling which will create data by duplicating samples , like SMOTE   will create new point from the two near points using linear interpolation ( choosing the points on the connecting line between the two near points).

    Core Idea:
    1. Pick a minority sample
    2. Find K - nearest minority neighbours.
    3. Create a new synthetic  point between those old connecting line using Interploation, its on linear line , so its linea interpolation.

    Mathematic formulae:
    --------------------
    x_new = xi + lambda [ xz (neighbour point) - xi (current point) ] , lambda => Uniform(0,1).

    Example , A = (2,3) and B = (6,7) [neighbour point from k nearest point ] 
    new point = (2,3) + 0.5(lambda) * [(6-2) , (7-3) ]
              = (2,3) + 0.5 * (4,4)
              = (2,3) + (2,2)
              = (4,5)  --> new synthetic point from interploation.

    Repeat this process for until minority samples equals the majority samples. thats it.

    Limitation of SMOTE:
    1. Overlapping classes ( If minority and majority are heavily overlapped , then it create confusions)
    2. Higher dimenstion Data ( Higher dimension nearest neighbour will unreliable SMOTE create unrealistic sample)
    3. Noise in minority ( if outliers in minotriy then it produce more outliers.)

### 1.4 Types of SMOTE:

### 1.4.1 Borderline SMOTE:
    SMOTE genearte samples in safe areas , noise area  , overlaping area , mostly its not upto use like generating more samples in safe regions like easily classified area. So why we focus everywhere?
    Why not focus only on near the decision boundary , this Borderline  SMOTE.

    Core IDEA : Generate Synthetic points for minority points only near the border line , near the class boundary. as points near 
    boundary are 
           1. Hard to classify
           2. More important for learning.

    ALGORITHM:
    ----------
    1. Find each minority sample and find its k nearest neighbours ( from whole dataset)
    2. look how many neighbours are from majproty classes
    3. Categorize minorty class based on neighbours
        All Neighbours minority                = Safe
        More than half neighbours are majority = Danger
        All neighbours are majority            = Noise

    4. Generate Samples only for "Danger" , why ? , safe points already in minority , noise -> mislabeled.
    5. Same SMOTE equation,  x_new  = xi + lambda ( x_neighbour - xi ) , but only for borderline minority samples.

    Types of Borderline SMOTE:
    1. Borderline SMOTE1: Interploate only with minority neighbours
    2. Borderline SMOTE2: Interpolate using both minority and majority., more aggressive.

    Disadvantage:
    1. When minority class heavily overlap majority.
    2. when over nosie
    3. very higher dimension Data.

 ### 1.4.2 SMOTENN = SMOTE + ENN:
    Its a hybrid class imbalance technique that 
    1. Oversampling  minority class( SMOTE )
    2. Cleans noisy data (ENN - Edited Nearest Neighbour )

    ENN:
    ENN its a Edited Nearest Neighbour
    It removes a **samples** if its label disagrees with majority of its k nearest neighbpurs.

    For example , if point A , is minority , and surrounding k neighbour points are all B , then A will get removed , as A will be Nosie for the model , and vice versa . 

    Disadvantage :
    1. If we more overlapping points, then it will remove the important features class too.

### 1.4.3 SMOTENC = SMOTE for Nominal (numeric) and Continous Feature.
    1. Its a Special version of SMOTE designed for dataset that contain both 
       Nominal ( age, salary )  and Categorical columns ( country , No.of.products , type)

    Why SMOTE fail for Categorical data?
    ------------------------------------
    for example , we having rank column (1 to 4) , then That Rank column will have number from 1 to 4, eventhough numbers its categorical means 1.5/3.2 is meanigless.

    If we apply SMOTE for such number , for example , 
    current point = 1 , neighbour_point =2 , Then SMOTE will create new point = 1.5 if lambda =0.5 , its pointless , there is no rank of 1.5 , the value will be update , but its nothing use for model learning.

    So , For categorical such number , we will not use SMOTE formulae , it will use mode selection of k nearest neighbours, if neighbout points are having rank 3 more, then  it will copy same.

    So , Fianlly
    For Numeric features     -> Linear interpolation ( regular SMOTE)
    For Categorical features -> Mode selction of data.

    **** We must specify to SMOTE NC , that Which column is categorical that need to create samples by mode."
    
### 1.4.4. ADASYN ( Adaptive Synthetic Sampling):
    Its an imporved version of SMOTE

    Generate more synthetic samples in regions where the minority class is harder to learn.
    SMOTE - generate samples uniformly.
    ADASYN - generate samples adaptively.

    Simply Adasyn focus on creating the more minotiy point near the boundary area , harder ones which are diffcult to model to learn.

    Steps
    1. Get minority samples
    2. Get difficulty Score,
    3. Generate sample like SMOTE in harger regions more, than the regular regions.

### 1.5 TOMEK Links
     if minority and majproty points are extremely close, they are lie on desicion boundary , what Tomeklinks do , it will remove the majority sample in the pair , minority stays, borderline majoriy gets removed.

     Mostly used with , SMOTE combined , SMOTE Tomek , 
     1. SMOTe ,  to increase the minority size equal as majority size.
     2. TOMEK , removes the majority lies  in the boundary area.

     TOMEK = Boundary cleaning
     ENN   = Noise Cleaning
     RUS   = Random reduction

## 2. Algorithmic level Techniques for Class Imbalancing:

### 2.1 Class Weighting (Cost - Sensitive Learning ):
    Most Common and powerful method
    here, instead of changing data , we change loss function

    Loss = Sum ( w_ . Loss (y,y_pred))
    here, w_ = weight value , but key is this
    
                           will be higher for minority class
    w_ (weight value ) => 
                           will be lower for majority class

    But , how , we calculating this weight value from this formulae

                     w_ =              N (total samples)
                           --------------------------------------
                              K ( no.of.class) * Nc ( number of samples for that particular class) 
 
    How this formulae created, basically
    our goal is if number of class lower , weight value higher, like wise versa , reason is to let the model put more weight for minority class so that it will not memorize the maximum class values. 
    
    So ,  w proportinal to  1/ (Nc(number of samples for particular class) [[indirectly proportional]]
        => w =  1/ Nc
    But its for 1 weight and its the concept
    Now total number of class_weight (C) = w * Nc 
    Now Total number of samples (N) = k * C
                               sub , c in above N
                               N = k * (w * Nc)
                               N/k = W * Nc
                             -- --------------
                             |  W = N/ K * Nc |
                             ------------------

    Thats the weight formulae, this tells the class weight value.

    we find this W value and then multiplywith loss , thats the adding weight to the loss function , that the Class weighting.

   ### 2.2 Focal Loss:
      Derived for highly imblanaced problems like ( object detection ) 

      Normal Cross entropy = -log (pt)
      Focal loss           = -(1-pt)^ focusing parameter log ( pt)

      Userd mainly in Retina Net.

  ### 2.3 Threshold moving:
      Instead of using 0.5 threshold 

      Default ,  y = 1 if p > 0.5.
      Imbalance ,y -1 if p > 0.3 
      This increases recall.


   ---------------------------------------------------------------------------------------------   
      
    

    

