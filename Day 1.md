# Statistical Learning

##Supervised learning 
 - Algorithm is given a set of specific targets to aim for. Target is known in advance. Aims to predict targets correctly.
 - Outcome measurement - Y - called as dependent variable/response variable/target variable
 - Vector - p measurements X - called as inputs, regressors, independent variables, covariates, features
 - Types of problems:
   * Regression problem - Y is quantitative variable. eg. Price, blood pressure
   * Classification problem - Y is a finite ordered set. eg. Survived/Died, Digit 0-9, Cancer class of a tissue sample
 - Training data: (x_1, y_1), ..., (x_N, y_N)
 - Observations are examples or instances of these measurements fed into the algorithm
 - Types - Categorical/Numerical ---> Categorical - classification problem --> Naive Bayes, Decision Trees; Numerical - Regression problem --> Linear regression, Penalised GLM
 - X1 - vector of p measurements
 - Y1 - Single response variable
 - eg. Imagine a child given lego blocks and taught to build a house, bike - patterns are taught - house with sharp edges, bikes with round edges
 - Formally:
    On the basis of training data, we'd like to:
       * accurately predict unseen test cases
       * understand which inputs affect the outcome and how
       * Assess the quality of our predictions and inferences
       * the idea is to know how and when to use these variety of techniques
##Unsupervised learning
 - Outcome variable is unknown, just a set of predictors available. It's not about predicting Y because there's no Y. Rather, learn about how the data is organised.
 - Find which features are important for the organisation of data.
 - Features are measured on a set of samples
 - eg. Child sees things no lables given. However, by seeing it repeatedly the child learns the patterns and to group the objects.
 - Here objective is fuzzy. We find a group of samples that behave similarly, find features that behave similarly, find linear combination of features with the most variation.
 - Difficult to know how well you are doing.
 - Different from supervised learning, but a useful pre-processing step to supervised learning.
 - eg. clustering of principal components PCA - important technique in unsupervised learning
 - Often useful to organise the features and choose it based on the X's themselves and then use these processed/chosen features as an input to supervised learning.
 - Lot easier- more common to collect data which is unlabeled and unsupervised. eg look for a movie on internet -> the algorithm can scan the web and grab reviews.
 - Figuring out whether the review is positive/negative often costs and takes human intervention to label data. 
##Philosophy
 - Aim is to not have just a laundry list of methods.
 - Important to understand ideas behind the techniques and know when and where to use them.
 - In our own work, there can be variety of problems that we have never seen before.
 - But, you should equip yourself to be able to judge which methods are likely to work well and which ones are not likely to work well.
 - Not just the prediction accuracy that's important. Important to try simpler methods in order to grasp the more sophisticated ones.
 - Linear models, linear regression, linear logistic regression - simple but effective ones.
 - Important to understand how well a method is doing. Easy to apply with a click of a software. But difficult & important to figure out how well is the method actually
   working so that you can tell that, when you apply this method, how well you're likely to do it tomorrow.
 - In some cases, you won't do well enough to actually use the method, and you'll have to improve the algorithm or may be able to collect better data.
 - Exciting area of research with new problems.
##Netflix prize example
 - Netflix has setup a competition to improve their recommender system's reting system by 10% of RMSE. Original algo had RMSE of 0.953.
 - Dataset: 400k customers, 18k movies
 - Each customer has rated on an average 200 movies each. Each customer has seen roughly about 1% of movies.
 - Think of it as a Big matrix that's sparsely populated with ratings 1-5. Try and predict what customers will think about the other movies based on what they rated so far.
 - Training data is sparse and roughly 98% of the data is missing.
 - $1m prize for 1st team that could improve their rating system by 10% by some measure.
 - took 3 years - winning team used PCA - Bellkor's pragmatic chaos
 - Rob & Trevor's team tries but hit with Computational issues. Computers not fast enough. (Common problem!!!)
##Statistical Learning vs Machine Learning
 - ML - subfield of AI; SL - subfield of stats
 - Commonality: both focuses on supervised and unsupervised problems
 - ML - greater emphasis on large scale applications & prediction accuracy
 - SL - greater emphasis on models, interpretability, precision and uncertainty
 - Distinction is often blurred & there is a lot of cross-fertilization between the methods.
 - ML - has upper hand in marketing with bigger grants and conferences.  

   
 
