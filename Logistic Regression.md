### Logistic regression
- Try to predict results of a binary (or categorical) outcome variable Y from a predictor variable X. This is a classification problem: classify X as belonging to one of two classes.
- Can transform predictor variable to something we can do linear regression on.
- logistic regression model.

#### Likelihood Functions for Log Regression
Can fit the model using MLE
#### Comments
Logistic regression is a modelling choice, posit it, then check whether it works or has systematic flaws.
- Tradition
- Often works surprisingly well as a classifier (But many simple techniques do that …)
- Closely related to exponential family distributions (which e.g. arise out of maxent)
- Is problematic if data can be linearly separated (if b,w perfectly separates linearly, so does cb,cw with c>0; so there is no parameter vector that maximises likelihood)
#### Non-linear Data: Fitting Polynomials
- Fit a polynomial instead of a straight line.
- Same idea as linear regression, just turning one predictor (X) into several (X2,X3, …). 
- Allows to deal with obvious non-linearity without having to specify in advance what transformation is 
#### Model reduction
- “Step-wise” model reduction. Either start with full model and reduce or start with simplest model and build up complexity. 
#### Kullback-Leibler divergence
- Measure of the informational distance between two probability distributions
- K-L distance between a real-world distribution and a model distribution tells us how much information is lost if we describe the real-world distribution with the model distribution. 
- A good idea to obtain a good model is to minimise the K-L distance to the real-world.
#### Akaike's Information Criterion
- If we had a true distribution F and two models G1 and G2 we could figure out which model we prefer by estimating K-L distances F-G1 and FG2. Don't know F in real world cases, but can estimate F-G1 and F-G2 from the data.
- AIC is an estimator for the K-L divergence. 
#### Limitations of AIC
- AIC is an asymptotic approximation.Number of params must be small compared to number of data points. 
- True model must be in the parameterised family 
- Every model in our family must map to a unique conditional probability distribution.
- Likelihood function must be twice differentiable
- Used for: Linear regression, generalised linear models, constant bin width histogram estimation 
- Dont use it for Multi-layer neural networks (uniqueness of p); Mixture models; The uniform distribution (differentiability)
