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
- We measure the error of a classifier using Misclassification error rate.

<img width="220" alt="image" src="https://github.com/user-attachments/assets/74f80760-74a5-4b4f-b513-2db2625cd026" />

- Measured on a test set. It is the average number of mistakes we make.
- Bayes classifier has the smallest error in the population.
- There are other ways to measure the error where you can have a cost, which gives higher cost of making some mistakes than others.
- Support vector machines - example which builds structured models for classifiers
- We can build structured models for representing the probabilities themselves. There are methods such as logistic regression, GAMs.
- High dimensional problems are worse for modelling the probabilities p_k(x) than it is for building the classifier. For the classifier, the classifier just has to be accurate to regard which of the probabilities is the largest. While if we are interested in the probabilities themselves, we are going to have to measure it on a finer scale.
- Let's consider a 2d example of nn.

<img width="364" alt="image" src="https://github.com/user-attachments/assets/368b59ea-9eca-4d9b-be0b-a7fe01b94194" />

- This represents the truth. We got x1 and x2. And, we got points from some population. The purple dotted line is the Bayes decision boundary. Since we know the truth here we know what the true probabilities are everywhere in this domain.
- All points in this domain are the little dots.
- If we classify according to the true probabilities, all the points, all the region colored orange would be classified as the one class. And all the region colored blue would be classified as the blue class. And the dotted line is called the decision boundary.
- That's a contour of the place where, in this case, there are two classes. It's a contour of where the probabilities are equal for the two classes. Decision boundary is an undecided region. 
- Do nearest neighbor, averaging in 2 dimensions.
- At any given point when we want to classify, pick a point and spread out a little neighborhood, (case of k = 10) say, until we find the 10 closest points to the target point. And we'll estimate the probability at the center point by the proportion of blues versus oranges. Repeat this at every point.
- And if you use those as the probabilities, you get a somewhat wiggly black curve as the estimated decision boundary. It gets reasonably close to the true decision boundary.

<img width="358" alt="image" src="https://github.com/user-attachments/assets/e271e42f-75d7-491f-86f1-fc21fffb302c" />
<img width="429" alt="image" src="https://github.com/user-attachments/assets/42af2993-a04f-4917-a72e-2c432fcf4133" />

- We can use other values of k. k equals 1 is common and is called the nearest neighbor classifier.
- Here we take literally at each target point, we find the closest point amongst the training data and classify to its class. The boundary here is a piecewise linear boundary. The probabilities that we estimate is just one and zero, because there's only one point to average. So there're no real probabilities.
- But if you think about the decision boundary, it's a piecewise linear decision boundary.
- It's the bisector of the line separating each pair of points when they're different colors.
- NN average approximates it in a noisy way.
- When we increase K to say K = 100, the neighbourhood becomes large. We get a smooth boundary. It almost becomes like a linear boundary and doesn't pick up the nuances of a boundary. k = 10 seems to be a good choice.
- So, the choice of k is the tuning parameter that needs to be selected.

<img width="427" alt="image" src="https://github.com/user-attachments/assets/441a39c6-3f03-4f94-8c26-0ffe7f347df2" />


- This image shows how the error rate varies when we vary k in training data and in test data
- on Training data, the errors tend to keep decreasing, not really in monotone
- k large => high bias; so, 1/k is small
- when 1/k is small => low complexity region; and when 1/k becomes large => high complexity region
- Towards the end, the error becomes 0 when 1/k = 1
- However, for test error, it starts increasing post 1/k = 0.01
- dotted line - Bayes error ie., you can't do better than Bayes error in theory
- test data set error rate - it touches the Bayes error rate at 1/k = 0.05ish and 1/k = 0.1ish
- Error rate in test set, decreases, levels off and starts to increase again. If we have a validation set, that's what we use to determine k.
- Eg. handwritten zip code problem - NN does as better as any other algorithm tried.
- other techniques include SVM, various forms of logistic and linear discriminant analysis.

