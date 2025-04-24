# Introduction to Regression Models

 What models are good for? How to use models? What are the issues around it?

-  Simple Regression model to predict sales based on three mediums namely, TV, Radio and Newspaper -
 Model: Sales $\approx$ f(TV, Radio, Newspaper)
-  We are trying to model the joint relationship between Sales and all three variables together to understand how these three variables operate together to influence sales.

- Sales: Variable Y, Response/Target we wish to predict/model.
- TV: one of the features or inputs or predictors X_1
- 3 predictors - notation is in column vectors
```math
Input \ Vector\  X\  = \begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}
```
Model is written as: 
```math
Y = f(x) + \epsilon
```
\epsilon captures the measurement errors and other discrepancies.

## What is f(x) good for?
* with a good f we can make predictions at new points X = x
* we can understand which components of X is important in explaining Y and which are irrelevant
* eg Seniority and Years of education have big impact on Income while Marital Status typically does not.
* Depending on the complexity of f, we may be able to understand how each X_i influences Y
* Is there an ideal f(x)? What's the good value of f(x) for any selected value of X. eg. at X = 4.
* Good value: f(4) = E[Y|X=4]
* This ideal value of f(x) = E[Y|X=x] is the regression equation.
```math
Y = f(x) + \epsilon = f(x_1,\  x_2,\  x_3) \ = \ E[Y|X_1\ =\ x_1,\ X_2\ =\ x_2,\ X_3\ =\ x_3]
```
- This is the function that minimises the mean-squared prediction error.
- f(x) = E[Y|X=x] is the function that minimises the error E[(Y-g(X))^2|X=x] over all functions g at all points X = x
- $\epsilon$ is the irreducible error = Y - f(x)
- Even if we knew f(x), we would still make errors in prediction, since at each X=x, there's typically a distribution of possible Y values.
- For any estimate fhat_x of f(x) we have E[(Y-fhat(x))^2|X=x] = {reducible error} [f(x) - fhat(x)]^2 + Var($\epsilon$)

## How to estimate f?
- Typically we have sparse data and actually no data points whose X = 4.
- So how do you compute conditional average? Relax the idea of "at point X" to "at in a neighbourhood of point X".
- fhat(x) = average(Y|X $\epsilon$ $N$(x)) where $N$(x) is the neighourhood of X.
- Nearest Neighbour (NN) averaging is pretty good for small p ie p<=4, with largish N
- Smoother versions: Kernel, Spline smoothing
- NN methods can get lousy when p is large. Why? _Curse of dimensionality_
- Nearest neighbours tend to be far away in high dimensions.
- Important to get a reasonable fraction of N values of y_i to average to bring down the variance eg 10%
- A 10% neighbourhood in high dimensions need no longer be local. So, we lose the spirit of estimating E[Y|X=x] by local averaging.

## Curse of Dimensionality
- Say, in 1D, I have below dataset:
- X = [10 9 14 30 100 5 32 -4 3 72]
- My query point is 4. How do I efficiently find the nearest neighbours?
- Linear time sequential search: Naive approach - take 4 and compare to each one and keep track of closest neighbor found
- time requires to search proportionally grows with the number of data points - not efficient!
- Another way to do efficiently in logarithmic time
- Binary search: Sort data into a new representation: X' = [ -4 3 5 9 10 14 30 32 72 100]
- Start at the midpoint - ask greater or smaller than the query point!
- How close are we to the nearest neighbour?
- 
  



  


 
