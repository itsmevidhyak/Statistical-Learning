# Structural Models

- Simplest structural model is linear model
- example of a parametric model
- f_L(x) = Beta_0+Beta_1.X_1+Beta_2.X_2+...+Beta_p.X_p
- p+1 parameters : Beta_0 to Beta_p
- Estimate the parameters by fitting the model to training data
- This gives a reasonable and interpretable approximation of the unknown true function f(X)
- Examples:
- Linear model: fhat_L(X) = betahat_0 + betahat_1.X_1
- Quadratic model: fhat_L(X) = betahat_0 + betahat_1.X_1 + betahat_2.X_2^2
- A quadratic model is also a linear model but it is linear in some transformed values of X.
- Linear fit:
<img width="296" alt="image" src="https://github.com/user-attachments/assets/a6e034eb-ce3c-466e-8ec0-c635bd0188ec" />


- Quadratic fit: Quadratic seems to fit better
  
<img width="292" alt="image" src="https://github.com/user-attachments/assets/5fff7003-fc34-44a8-8bc5-c2a1849cdb4a" />

- 2D Example: income = f(education, seniority) + $\epsilon$ (The red points are simulated values of income. f is the blue surface showing the true function simulated from data with errors. We can see the errors are not big.)
  
<img width="326" alt="image" src="https://github.com/user-attachments/assets/df54aa77-9a81-43d8-88b1-f7e1fc35ac31" />

Linear regression: fhat_L(education,seniority) = betahat_0+betahat_1.education + betahat_2.seniority
Approximation that captures important elements of the relationship - but doesn't capture everything

<img width="326" alt="image" src="https://github.com/user-attachments/assets/a2f83c10-01b0-49bb-9f9b-aa4b1f4323e1" />

Flexible regression model: Thin-plate spline : fhat_S(education, seniority) with flexible surface
Nice smooth version of 2-d smoother
Does a good job  - captures more essence of what's going on
It has a tuning parameter on how to smooth the surfaces and to control the complexity.
We got a family of functions and we've got a way of controlling the complexity. Some tradeoffs are there while building the models.

<img width="320" alt="image" src="https://github.com/user-attachments/assets/6bd33505-8008-4f42-a0eb-2d2dca815c6b" />


  ## Tradeoffs

  ### Prediction accuracy vs interpretability
  1. Linear models are easy to interpret and we have got a few parameters. While, thin plate splines are not.
  2. Thin plate splines give the surface but if you get a surface in 10d it becomes hard to interpret.
  ### Good fit vs underfit vs overfit
  4. In above example, linear was slightly under-fit. Thin plate spline was good fit. But when we tuned the parameter to achieve zero error, we see a over-fit.
  5. How do we know when the fit is just right?
  ### Parsimony vs Blackbox
  6. Simpler models with fewer parameters or black box model involving them all?

 <img width="429" alt="image" src="https://github.com/user-attachments/assets/97b9596a-9d0d-4f11-bb4b-0814119b0687" />

    

  



