# Decision Tree

Decision Tree is the Supervised learning Algorithm used in 

1. Classification
2. Regression

It splits data into smaller subsets based on the feature values.
It simply like a Flow chart of Yes/No question leading to a decision making.

## Structure of Tree:

- Root Node : Starting point
- Decision Node : split based on the condition
- Leaf node : Final output ( class /  Value )
- Branches  : outcome of decisions.

## How it works:

- Select the best feature based using Gini Impurity or Entropy Score ( Classification problem) and Mean squared Error ( for Regression Problem)
- Find Split and threshold condiiton based upon the above value
- Split data based on a condition.
- Repeat recursively until the stopping condition met.

## Spliting Criteria :

### Classification Problem:

#### 1. Gini - Impurity:
It measures the impurity value , Gini Tells how oftena random sample is miss classfied.

Formulae = > Gini = 1 - Summation ( Pi ^2) [Pi = P0 ^2 + P1^2 ]

Pure Node -> Gini = 0
Mixed node -> Gini = inceases.

So , 
Lower Gini - Good split
Higher Gini - Bad Split

Gini Pure set -> Gini value -> 0
Gini max impure -> Gini value -> 0.5
so Gini range is 0 (pure)  to 0.5 (very Impure) 

#### 2. Entropy - (disorder measure) - (uncertainity):
- Entropy tells how mixed the data is
- More mixed - More Entropy
- Pure  -> Entropy = 0
- Max impure -> Entropy => 1
- so Entropy range is 0 (pure) to 1(very impure)

      Entropy = - Summation (pi * log2(pi))


## Stopping Condition:
Tree creation will be stopped when

1. Max depth reached
2. Minimum samples in node
3. Pure node( all same class / average = 0)

## Hyper parameters of Decision Tree:

1. max_depth - Controls overfitting
2. min_samples_split - min samples required to make a split
3. min_samples_leaf - min samples at leaf
4. criterion - 'gini' or 'Entropy' ( classfication) / Mean squarred error ( regression )

## Advantages:

1. Easy to understand visualize
2. No need for feature Scaling
3. Handles non linear relation

## Dis-advantage:

1. Overfitting
2. Sensitive to small data changes
3. Low generalization.

## Overfitting in Decision  Tree:
Trees can grow very deep and memorize data.

Solutions:
1. limit : max depth
2. increase :min_samples_leaf
3. pruning

### Classification Tree -> Class label -> Gini / Entropy
### Regression Tree -> Continous value -> Mean Squarred Error

### One full Example:
  
