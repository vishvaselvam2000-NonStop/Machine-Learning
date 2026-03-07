# Stochatic Gradient Descent:

1. Draw Training sample x and target y_true
2. Run model on x to obtain y_pred
3. Compute Loss ( y_pred and y_true )
4. Compute gradient of loss with respect to the model coefficients ( weight and biases )
5. Move the weight a little in opposite direction from the gradient.

   w_new  = w_old - learning_rate * Gradient.

Limitation of SGD:

1. Slow convergence in flat regions.
2. Oscillate in Steep regions
3. Get stuck in Local minima.


# SGD with Momentum:

Improve the gradient descent by using memory of the previous weight updates.
Weight updation  consider not only current gradient but also the previous weight update movement.

Previous weight update/ memory of the past gradient => Velocity

#### Type 1 of using velocity in GD:
     Velocity = beta * Velocity + gradient_of_tensor
     W_new = w_old - learning_rate * Velocity.

#### Type 2 of using celocity in GD:
    velocity = beta * Velocity - learning_rate * gradient_of_tensor
    W_new = w_old + velocity.

beta is percentage of using old velocity 
if beta = 0.9 , SGD consider 90% of old weight update + 10% of current gradient update.
Both Type 1 / Type 2 are equal algebrically , only the placement will be very.

### Advanage of SGD with momentum:

    1. Reduce Oscillations in Steep slopes.
    2. Accelerate movements in Shallow Slopes.
    3. Smooth Update, avoid Abrupt Change.
    4. Escape Local minima easily.
    5. Add Innertia , Keep moving in consistent gradient descent direction.
    


