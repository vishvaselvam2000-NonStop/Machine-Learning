# Logistic Regression

- Its the Classification model which gives the probablity score for each class sum to one.
- Its uses gradient descent algorithm to optimize the weights.
- Its uses Cross entropy as the loss function
- Its needed feature scaling as distance mater for gradient calculation , and also for faster convergence.

## Understanding:

Base is from Linear Regression 

1. Linear regression solves z = wx + b  / or in genral vector form ( z= w pow T x + b) , as t dentoes number of features , it gives the value from -infinity to + infinity scalar numbers , actually it used for Regression
Type of problems

2. Here we uses Sigmoid function which change the output range from  -Infinity to  +Infinity ---> 0 to 1 range (Probablity)
3. So Formulae = 1
4.              ----
5.               1+ e^-z   ( z = wx + b ) 
6. **This gives y_pred , So y_pred = 1/1+ e ^-( wx+ b )**
7. So Once we obtian y_pred, it will be in the range from 0 to 1 , The actual value would be approximate , not exact one , even for
Very large number it will approx one and veru small negative number it will approx 0 .
8. The Loss function we will use for logistic regression is Cross-Entropy the reason is
        As Bernouli distribution , p ^ y ( 1-P) ^ 1-y , take log and add minus then thats binary cross entropy --> 
10.      loss_function = - [ y_trur log(y_pred) + (1-y_true) log(1-y_pred)]
        y_true = True Label
        y_pred = Predicted label
        Here,
        We use log magnify / penalize , as
        if true label is 1 , if      pred is 0.7  --> loss value would be lower ( penalize )
                             else if pred is 0.1  --> loss value would be very higher ( magnify )
        Why log?
        --------
        Probability closer to one -- log is close to 0 -- loss small
        Probability closer to zero -- log is very infinity -- loss large
        value close to one -->    log will give less number
        value closer to zero -->  log will give higher number

        If true label is 1
        -------------------
        the we expect value higher like  0.8,  very less loss  value
         So we can calculate loss =   y_true *  log(y_pred)
         as y=1 , so 1* log(y_pred) = log(y_pred)
         if y_pred = 0.8 , log(0.8) = -0.223 , approx = -0.2 , as we expect loss value is less for 0.8
         if y_pred = 0.1 , log(0.1) =  -2.3 , approx = -2.3 , as we expect loss vlaue higher  for 0.1
         
         If true label is 0
         ------------------
         We expect value lower like 0.2 , very less value
         So we invert it , hence loss = (1-y_true) * log(1-y_pred)
         as y=0 , so (1-0) * log(1-y_pred) = log(1-y_pred)
         if y_pred = 0.2 , log(1-0.2) = log(0.8) = -0.223 , approx = -0.2 , as we expect loss value is less for 0.2.
         if y_pred = 0.9 , log(1-0.9) = log(0.1) = -2.3 , approx = -2.3 , as we expect loss value  is high for 0.9

         But on the two we got what we expected , but values are in minus , its false, model expect positive value and also We cant do
         if condition like if y = 1 , then loss = y * log(y_pred)
                           if y = 0 , then loss = (1-y) * log (1-y_pred)
          So we add together for both the average as it contain both classes.
     
                           loss = y_true *log(y_pred) + (1-y_true) * log (1-y_pred)
     
                           Hence if y =1, then y*log(y_pred) will consider, as (1-1 = 0 ) will cancel.
                                 if y =0 , then (1-y)*log(1-y_pred) will consider , as (0*logy_pred = 0) will cancel.
          But eVenthough we miss one the value of the log will always in negative for number from 0 to 1 but we want plus direction
           We simply multiply with minus

           Hence         loss = - [ y * log(y_pred) + (1-y) * log(1-y_pred) ]
           Thats the Cross entropy.

   ## Process of the model internal:
       1. First we set a random variable for w and b , then forward pass
       2. Then , z = wx+ b
       3. Use sigmoid function , y_pred (or) loss= 1/1+e^-z
       4. Compute loss for y_pred and y_true using cross entropy ( loss = -[y * log(y_pred) +  (1-y) * log(1-y_pred)])
       5. Gradient Calculation:
          dloss / dw = dloss / dz * dz/dw ( chain rule )
          dlos/dz = y^ - y ( its derived from differentiatio of sigmoid function and also algebric operation)
          dz/dw = x ( w and b are consant )
          Hence => dloss / dw = (y^- y) * x
          also, => dloss / db = (y^ - y)
       6. Weight Update:
          new_w = old_w - learning_rate * (y^ - y) * x
          new_b = old_b - learning_rate * (y^ - y)
       7. Again Forward pass => y_pred => loss calculation => Weight Updation (Backpropagation )
       8. loop runs until , slope =0 , or model attain the lowest point where the gradient = 0 or very less loss value.

    ## why we not using mean squared error:
        1. If mse then , loss = 1/2 ( y_pred - y ) ^2
        2. y_pred = sigmoid (z)
        3. dl/dz = (y_pred * y) * d(sigmoid)
        4. d(sigmoid) = y_pred(1-y_pred)
        5. So graident become , ( y_pred - y) * y_pred(1-y_pred)

        If y_true = 1, y_pred = 0.01
        then, y_pred(1-y_pred) = 0.01
         So gradient become , (-0.99) * 0.01 = -0.009
        Very Tiny Update ,  model lean very slowly ,  wrong prediction not corrected strongly.
    
    ## Why Cross entopy:
        1. L = -[ y * log(y_pred) + (1-y) * log(1-y_pred) ]
        2. dl/dz = y_pred - y
        if y_true =1 , y_pred =  0.01
        grad _to _ z= 1-0.01 = -0.99
       Strong correction , faster learning , No Vanishing gradient.

     

Thats the Logistic Regression.
