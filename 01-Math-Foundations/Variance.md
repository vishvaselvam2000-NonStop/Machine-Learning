# Why Variance:

Dataset A => 50, 50, 50, 50, 50
Dataset B => 10, 30, 50, 70, 90

Both Dataset have same Mean = 50
But on Dataset A , values are all similar
On Dataset B , the values are all spread out.

So we need to measure

**How spread out is the data from the mean**
That is called Variance.

## Variance:
How far each data is from its mean , center is called Variance.

If data is very spread      -> Variance is high
If data is very less spread -> Variance is low


## Variance
Variance is how far each data is from its mean

here 
1. Mean
2. How far distance of each datapoint from the mean.

1. Find mean

        Mean = Summation of x / n

2. Distance from mean:

       Sumation ( x - mean) , it will result 0 , hence to preserve the distance  we squared it.
       => Sumation (x - mean) ^2


3. Now Average the Squared differences , hence the Variance formulae is
      sigma^2 => Summation ( x - mean)^2 / n  
