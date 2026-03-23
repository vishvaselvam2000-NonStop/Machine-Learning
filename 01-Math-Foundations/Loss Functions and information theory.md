# 1. Entropy:

Entropy measures uncertainity in the data.

            H(P) = - Summation ( p * log(p))

### Intution:
1. Pure Data  -> entropy = 0
2. Mixed Data -> entropy = high

Its just tells how uncertainity is the dataset?

USE of LOG HERE:
- Convert probablity -> Information
- Rare event         -> High Information


# 2. Cross- Entropy:

Measure How wrong prediction is compared to true Distribution.

          H(p,q) = - Summation(p * log(q))

          p-> True      value
          q-> Predicted value
          How far prediction is from the truth.


## Key insight
- If prediction = true ->  Low loss
- If prediction = wrong -> High Loss


# 3. KL Divergence:
Measures difference between true and predicted distributions

DKL(P||q) = Summation ( p log(p/q) )
Cross-Entropy = Entropy + KL_Divergence.
On Cross Entropy , Entropy is actually a consant , we only measuring the KL Divergence for Cross entropy


# 4. Logarithmic Function:

log(x)

- Compress values
- Convert multiplication -> Addition
- Used in Entropy
- Used in Cross Entropy

# 5. Exponential Function:

e^x

- Expand values
- Amplifies Error
- Used in Adaboost
- Used in Exponential Loss
- e = 2.718
- d/dx (e^x) =e^x

# 5. Binary CrossEntropy:

L = -[ y log(y_pred) + (1-y) * log(1-y_pred)]

if y =1 , then -log(y_pred)
if y =0 , then -log(1-y_pred)


 # 6. Multi - Class Cross Entropy:

 L = -Summation(y * log (y_pred))

 - only correct class contributes.

# 7 . Exponential loss function:

          L =   e ^-yf(x)

          Punish wrong prediction heavily
          if is correct gives small output
          if is wrong it punish with very large number

          

