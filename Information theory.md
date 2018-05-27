### Entropy
- Entropy of a distribution is the expectation of information of the distribution or the average surprise when sampling from the distribution.
- Shannon theory
#### K-L Divergence
- Compares the entropy of two distributions over the same random variable 
- Heuristically: number of additional bits encoding a random variable with distribution f(x) using g(x)
#### Realized information
Let's say we have two random variables C and X which are not independent. So if we observe one feature in X this will change our knowledge about C, i.e. if we observe x our uncertainty about C changes by the conditional entropy. The difference between the entropy of H[C] and the conditional entropy H[C|X] is realized information.
#### Mutual information
Mutual information is the expected information a feature gives us about a class.
https://blog.csdn.net/ranghanqiao5058/article/details/78458815
