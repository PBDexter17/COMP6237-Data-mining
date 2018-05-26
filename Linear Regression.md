## What regression analysis is about
What about if we want to predict the value of one variable based on the knowledge about another variable.
- When to use? Predict continuous/ordinal variables

#### Type of variables
- Continuous: real numbered values
- Ordinal: school grades, Michelin stars
- Categorical: country of birth, gender, etc

#### Dependent or outcome variables
It is assumed to be predictable from some other variables
#### Independent or predictor variables
Use them to explain the variance in the dependent variables

#### Variables in Regression
- One dependent Y and one independent X variable
- Both variables are continuous
- Predict the variation in Y based on the variation in X

### Method of Least Squares
- For any given line mX+b we can measure the difference between our actual Y values and those predicted
- Squared differences are a reasonable measure of the goodness of fit and regression analysis tries to minimize this difference
b=E[X]-mE[X]    m=Cov[X,Y]/V[X]
#### Machine learning model
- Consider the pairs(Xi,Yi) as a training set
- Learning a mapping y=f(x) from the training set
- try to learn best parameters m and b, this is often done via minimising some error function E which sums up squared residual errors over training set.
#### Residuals
- It is differences between predicted output and actual output. It should roughly be normally distributed with a mean of zero.
- Coefficients: m and b
#### Other output
- R-square value and adjusted R-square value to account for the fact that models with more parameters are expected to perform better.
*The R-squared statistic provides a measure of how well the model is fitting the actual data.*
- F-statistic. Finish with an F-test on the model as a whole with degrees of freedom 1 and 98 - tests the significance of the model.
*F-statistic is a good indicator of whether there is a relationship between our predictor and the response variables.*
#### Maximum Likelihood Estimation
- Suppose we have a set of n data points X1,...,Xn which are from some probability distribution function f(x;p) which has some hidden parameters, p. We want to guess it. 
- Least squares is equivalent to an MLE estimate for m and b if X and Y are linearly related with Gaussian noise.
#### Why weighted Least Squares
- To focus accuracy – might be more interested in certain X-regions, or errors in some regions might be more costly than in others. *Some Xs might be more important.*
- There is a number of other optimisation problems transformed/approximated by WLS, e.g. generalised linear models where the response is some nonlinear function of a linear predictor (e.g. logistic regression, see later)
#### Homo-/Heteroskedasticity
- Discounting imprecision.
Ordinary least squares assumes Gaussian white noise has constant variance (homoskedasticity). Often this is not the case.
- Does not make much sense to concentrate on noisy parts of the data, want to use parts with little noise for our estimates.
#### How to know the proper weights?
Use weighted regression performs better than unweighted regression.
- Somehow know it from measurement device (e.g. know precision of the devise for various ranges)
- E.g. in polls or surveys variance of the proportions we find should be inversely related to sample size, hence can make weights proportional to sample size. 
- Try to estimate it from the data.
### Local Linear Regression
what if the relationship is not linear? 
- Naive approach: use some window (say of size h) around data points and then use weight least squares.
- Kernel regression
