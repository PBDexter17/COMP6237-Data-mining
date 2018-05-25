## What regression analysis is about
What about if we want to predict the value of one variable based on the knowledge about another variable.

### Type of variables
- Continuous: real numbered values
- Ordinal: school grades, Michelin stars
- Categorical: country of birth, gender, etc

### Dependent or outcome variables
It is assumed to be predictable from some other variables
### Independent or predictor variables
Use them to explain the variance in the dependent variables

### Variables in Regression
- One dependent Y and one independent X variable
- Both variables are continuous
- Predict the variation in Y based on the variation in X

## Method of Least Squares
- For any given line mX+b we can measure the difference between our actual Y values and those predicted
- Squared differences are a reasonable measure of the goodness of fit and regression analysis tries to minimize this difference
b=E[X]-mE[X]    m=Cov[X,Y]/V[X]
### Machine learning model
- Consider the pairs(Xi,Yi) as a training set
- Learning a mapping y=f(x) from the training set
- try to learn best parameters m and b, this is often done via minimising some error function E which sums up squared residual errors over training set.
