# Model Accuracy

- Fitted function: fhat(x) to a training data
- Tr = {x_i, y_i} i in 1 to N, where x may be a vector and y is a scalar
- Average mean squared error prediction error over the training data:
- MSE_Tr = average i in Tr {y_i - fhat(x_i)}^2
- Average mean squared error prediction error over the test data:
- MSE_Te = average i in Te {y_i - fhat(x_i)}^2 where Te = {x_i, y_i} i in 1 to M
- MSE can be biased towards overfit models. So, testing the fit on a hold-out test set can be a better indicator of the performance of our model.

- In the fit among different models, there is a point at which the MSE is minimal.

- <img width="422" alt="image" src="https://github.com/user-attachments/assets/c462cfd9-8154-4346-9652-3ada4fc6dbbe" />

- Horizontal dotted line - this is the mse that the true function makes for data from this population. This is the irreducible error - variance of epsilon.

# Bias-Variance tradeoff

- say fhat(x) is the fitted function of training data Tr
- True model: Y = f(X) + $\epsilon$
- where f(x) = E[Y|X=x]
- Variance = E(Xsq) - Esq(X)
- let (x_0, y_0) be the test observation drawn from the population
- Look at the expected prediction error of fhat at x0. That's the predicted model. Fitted model on training data evaluated at new point x0 and see what's the expected distance from the test point y0. This expectation averages over the variability of the new y0, as well as the variability that went into the training set used to build fhat.
- This gets broken down in the below derivation in the next section.
- one piece is the irreducible error => It comes from the random variation in the test point y0 about the true function f.
- Two reducible pieces:
* Variance of fhat - Variance that comes from having different training sets. If I get a new training set and fit the model I get another fhat. If I look at many many different training sets, there would be variability in my prediction at x0.
* Bias of fhat - difference between the average prediction at x0 averaged over all these training sets and the true function f(x0).
- As the flexibility of fhat increases, typically the variance increases and bias decreases. Because you are going after the individual training set provided which would be different from the next training set. But its bias decreases. 
* Low flexibility means close to a linear fit => the model doesn't react much to the changes in training data.
* Increase in flexibility -> model overreacts and absorbs the random noise present in the underlying training set.
* Small changes in data can lead to large changes in fitted function fhat.
* eg fitting using a higher degree polynomial
* Bias decreases because we are getting close to the true function and hence, the distance tends towards 0.
* Choosing the flexibility based on average test error amounts to a bias-variance trade-off.

* Assignment qn:
* A fitted model with more predictors will necessarily have a lower Training Set Error than a model with fewer predictors. T/F?
* Answer: F, While we typically expect a model with more predictors to have lower Training Set Error, it is not necessarily the case. An extreme counterexample would be a case where you have a model with one predictor that is always equal to the response, compared to a model with many predictors that are random.
* While doing a homework assignment, you fit a Linear Model to your data set. You are thinking about changing the Linear Model to a Quadratic one.
* Answer: Introducing the quadratic term will make your model more complicated.
* More complicated models typically have lower bias at the cost of higher variance.
* This has an unclear effect on Reducible Error (could go up or down) and no effect on Irreducible Error.

# Bias variance tradeoff derivation

![01  Variance](https://github.com/user-attachments/assets/caf54cc9-6ade-44e6-9b63-3cc75d5f6e1d)

![02  Derivation](https://github.com/user-attachments/assets/c70e8aa0-9fd4-4241-8c6d-c6182aaa35f8)

![03  Derivation](https://github.com/user-attachments/assets/6532e4a2-e178-4647-9bc1-8c00dfaaab7e)

![05  Derivation](https://github.com/user-attachments/assets/1fd8c5be-694f-4844-a740-918ca4511ddb)


