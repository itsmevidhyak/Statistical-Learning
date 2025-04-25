# Curse of Dimensionality

- issues that arise when the number of datapoints is small relative to the intrinsic dimension of the data
- perennial challenge for all pattern recognition problems
- Nearest neighbour methods are lousy when p is large due to curse of dimensionality
- NNs tend to be far away in high dimensions. We need a reasonable fraction on N values of y_i to average in order to bring the variance down.
- We need to average the number of points in a neighbourhood so that estimate is nice but also the variance is reasonably small.
- Eg. Visualise how the distance to the corner behaves as the number of dimensions increase
 Distance to corner = sqrt(side ^ 2 * Number of Dimensions)

![image](https://github.com/user-attachments/assets/d151b48f-1b78-45cb-8245-c89e9a3f241b)


- Consider a (-1,+1) little cube
- say we got 2 variables x1 and x2
- assume they are uniformly distributed in this space
- we form a 10% neighbourhood. 1st neighbourhood by keeping x1 and ignoring x2 & say, the target is 0. You would get a vertical line in graph and we spread out to a neighbourhood +/- 10%.
- Now, if we consider a circle centered at the target point spread out in such a way we capture 10% of the neighbours.
- Radius of circle in 2d > Radius of circle in 1d which is the width between the two lines
- So, to capture 10% of points, we need to spread out more to in 2d and we become less local than that in the 1d.
- Second chart shows how far we need to go as dimensions increases. As dimensions increases, neighbours get concentrated at the corners.
- You need to travel more to capture the 10% of the neighbourhood.

![image](https://github.com/user-attachments/assets/0f39073d-505a-441f-bf91-c5caf54657d9)

# How do we deal with this?
- Introduce structure to the models
- Simplest structural model - Linear parametric model

