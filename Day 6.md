# Classification

- Response variable Y is qualitative
- eg. email classification problem - two classes ie., spam or ham
- C = {spam, ham}
- Digit classification problem 
- C = {0, 1,..., 9}

## Goal
- Build a classifier that assigns a class label from set C to a future unlabeled observation X where X is a feature vector
- Assess the uncertainty in each classification
- Understand the roles of each predictors among X = {X_1,..., X_p}
- Simulation example with 1 X and 1 Y. The responses are coded as 0 and 1. Each bar indicates an occurrence of 0 or a 1 as a function of X. Scatter plot is hard to read. 

<img width="417" alt="image" src="https://github.com/user-attachments/assets/2bd921f2-c470-4b38-bf5e-950aa17ad924" />

- Black curve - generated from the data. It shows the probability of a 1 along X = 6 to 7 is close to 90%.
- Useful for interpreting high density areas.
- Think whether is there an ideal classifier C(X)?
- Support K elements are in C, numbered 1,2,...,K. Let,
- p_k(x) = Pr(Y=k|X=x), k = 1, 2,..., K.
- These are conditional class probabilities at X. eg. A little bar at x = 5.
- Bayes optimal classifier at x, C(x) = j if p_j(x) = max{p_1(x), p_2(x),..., p_K(x)}
- In the chart, we have seen only the probability that k = 1 with 2 classes. In general, there can be k classes. There will be K conditional probabilities. This captures completely the conditional distribution of Y|X. This delivers an ideal classifier. This is called as Bayes optimal classifier because it classifies to the class the conditional probability for that element of the class is largest.
- This makes sense - you go to any point. Say point 5, P(Y=1) = 0.8 and P(Y=0) = 0.2. Here you'd classify it to the majority class of 1.
- Same example but take only 100 points. We can't compute the conditional probability at exact point say x = 5. We got a 1 at 5 and no 0s. So, start looking at around 10% of the neighbouring data points. Then estimate the conditional probability by the proportions in this case of 1s and 0s in the neighbourhood -> indicated by the small bars in the below chart. The proportions at point x = 5 shows higher probability of 1s than 0s estimated with the nearest neighbour average.

<img width="421" alt="image" src="https://github.com/user-attachments/assets/dc6c2274-71ef-42f1-943b-2545b5c14d48" />

- This is in 1 dimension. This can work for multiple dimensions as well. Say now we have two Xs lie in the floor with a target point and we want to classify a new point. You can draw a circle and spread out a circular neighbourhood and gather a bunch of observations that fall in the neighbourhood. Count how many 1s and 2s and assign it to the majority class. This can be generalised to multiple dimensions. 
- Curse of dimensionality is applicable for classification problems as well when the number of dimensions get large. 
- In order to gather enough points we need to send out a bigger and bigger sphere to capture the points.
- Things start to break because it ceases to remain local anymore. 


