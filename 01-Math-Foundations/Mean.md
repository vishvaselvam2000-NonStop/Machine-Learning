# Mean:
Imagine if we have 25 student in class , and we have 25 marks , now if someone asks "what is the typical mark / Average mark of this class?

We want one number that represent all the numbers , its the center balancing point of that data.
The Solution is MEAN

**MEAN == Average value**

Another example:
----------------
i have 5 firends and choloclates
2,4,6,8,10 chocolates
IF we distribute equally among 5 friends
=> total_chocolates / Number of friends
=> 30 / 5
=> 6
We can give 6 chocolates equally to all the friends , that is mean , thats average , thats balancing point.

## MAthematical Formulae:
    Mean =   Sum of all values
           ----------------------
             Number of values


## MEan for ML:
     - Mean is the Center balancing point
     - In ML , for regression we often ask , what is the best predicted value for thi data?
     - Thats mean
     - We mut guess one predicted value which result the least squared difference is none other than , its MEAN.

## Mean Minimizer Squared Error:
    - In Regression , we choose eman because it minimize squared error ( y - y_pred ) ^2.
    - when We squared and minimize eror the best ped value would be mean.
    - Thats why mean used in 
      1. Linear regression
      2. MSE Loss
      3. Variance
      4. Deep Leanring.


## Why least squared difference value is mean , Mathematically:

Total Squared Error  E(x_pred) = Summation of ( xi - x_pred) ^2
Our Goal                       = Find x_pred that minimize the E(A).

How we find leat error value that E(A) contains , its simple take derivative of E with respect to x_pred, this tells how far x_pred
varies , E aries , and here the chance of getting least value is ( **SET Derivative = 0**)

      E = (x - x_pred) ^2
      taking derivative w.r.t x_pred
      dE/dx_pred = d/dx_pred( x - x_pred) ^2
                 = d/dx_pred ( x^2 + x_pred^2 - 2*x*x_pred)
                 = d/dx_pred (x^2 -2x_pred(x) + x_pred^2
                 ....use derivaive
                 = 0 - 2 * x + 2x_pred
      We miss the summation            
                 = 0 - 2 summation(x) + 2n*x_pred
      dE/dx_pred = 2nx_pred - 2 summation(x)

     Now this the derivatve, our goal is minimum , so set derivative =0
    2nx_pred - 2 * Summation(x) = 0
    ,, Divide both side by 2
    2nx_pred -  2*sumation(x) = 0/2
     -------------------------
             2

     2( nx_pred - sumation(x) )  = 0       
    ---------------------------
               2

    2 will get canceled both side numerator and dinominaotr
      nx_pred = summation(x)
      x_pred = summation(x)
              ------------
                   n

      Its none other than , is the mean formulae 
      So if the predicted value is mean , then squared error value will be very minimum , this the least, So if we need to find the
      Continous value for the data , we actually need to find the mean , which gives least squared difference and that represent all the
      value.

      






      


    
