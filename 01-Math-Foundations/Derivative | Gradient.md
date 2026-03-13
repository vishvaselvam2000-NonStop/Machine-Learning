# Derivative / Gradient:

### Slope of Straight line:

    y2|----------------*
    | |                |   
    y1|-----*          |       [ Straight line will be passing from (x1,y1) to (x2,y2) ]
      |     |          |
      |_____|__________|__
           x1  ----> x2
     
     Here (x1,y1) point is changing to x2,y2 , here small epsilon x change happen so that small change epsilon y will be approximate as
     ep_y = m(slope of line) * epsilon_x.

     But HOW?

     Slope = Rate of change 
     slope of x = rate of change with respect to x variable

     Slope = y2 - y1                 Rate of change in y
             --------               ---------------------
             x2 - x1                 Rate of change in x

    Slope will be constant in the straight line , there is no abrupt angles so slope is constant for linear line / straight line.

### Slope of Curve:
    y = f(x) = x^2:
    
    |    *               *
    |    *               *
    |    *               *
    |     *              *
    |       *          *
    |         *      *
    |____________*________________

    - It not a straight line
    - Slope will be varying at each point of the curve.
    - we need to find slope for every new point in the Curve.

 ### To find Slope of point p in curve of f(x) = x^2:
    - To find instantaneeous slope of point P  in curve. that is instant slope at that point wether its on upward or downward we can find.
    - To find slope , we need two points for slope formulae
    - But here only one point p , and we need to find instantaneous rate of change , so we need another point.
    - We consider one imaginary point P1 near point P that is secant line
    - We moving that secant line to as close enough to Point P , we are moving as much as possible very near , only very minute difference.
    - If so , If epsilon p(difference from p to p1)  is as close enough at point p , then we can approximate of linear function of slope
    hence the finding slope is instantaneous rate of change at point p , as p1 is very close, its the slope at point p. 

    - The epsilon p is almos zero , very close.

    ***
    
    y = f(x^2)
    Find slope at particular point.
    f'(x) = ^y / ^x
    x = x
    epsilon x = h(we seting new secant line where its difference h as close to zero) , 
    so old point x = x
    so new point x1 = (x+h)

    ....
    x1 = x
    x2 = x+h (h-->0)
    y1 = f(x^2)
    y2 = f(x+h)^2
 
    f'(x) = y2-y1            f(x+h)^2 - f(x^2)
            -------   ===>   --------------------
            x2-x1                 (x + h) - x

          = x^2 + h^2  + 2xh - x^2
           -----------------------
                 x - x + h
    
          = (denominator x and x will cancel , nominator => x^2 and -x^2 will cancel)
          = 2xh + h^2                h(2x + h)
            -----------     =       ---------
                h                       h
          = (h and h will cancel)
          = 2x + h
         *** Now as its new point is very much close to point p , the difference h is close to zero ***, h->0
         hence,
         = 2x + 0
      ______________
        f'(x) = 2x |
      ______________

      This the derivative of f(x^2) at a point p, yeah this the formulae nx ^n-1 , thats the general formulae  for x ^n differentiation.
      This the instantaneous slope of point p.
      This will tell on which direction we need to move our weights to reduce loss score.


  ### Identitical formulae
      Slope f'(x) = rate of change of y  / rate of change of x.

      i.e is  f'(x) = ^y / ^x
      now multiply ^x on both the sides
      ^x * f'(x) = ^y/^x * ^x
      ^x * f'(x) = ^y [^x will got canceled ]

      thats the ^y = ^x * f'(x)


      ***END***

 ## Gradient:

 Derivative of Tensor is called Gradient, 

 - f(x) = y         => scalar x to scalary y             => 2d plane.
 - f(z) = x^2 + 2y  => tuple of scalars(x,y) to scalar z => 2d surface in 3d plane.
 - If function take matrices as input => n number pf palnes

 For all Such Gradient would apply as long as the function is derivative.

    
