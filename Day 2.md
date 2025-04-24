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

- What is f(x) good for?
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
- \epsilon is the irreducible error = Y - f(x)
- Even if we knew f(x), we would still make errors in prediction, since at each X=x, there's typically a distribution of possible Y values.
- For any estimate fhat_x of f(x) we have E[(Y-fhat(x))^2|X=x] = {reducible error} [f(x) - fhat(x)]^2 + Var(\epsilon)
- 

  


 
