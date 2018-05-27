### Collaborative Filtering
#### Collaborative Filtering Task
- Discover patterns in observed preference behaviour (e.g. purchase history, item ratings, click counts) across community of users 
- Predict new preferences based on those patterns 
- Collecting user preferences. Need to make measurements of user preferences. 
- Mapping user actions to numerical scores. Many different ways to map user preferences to numerical scores. Will depend on the variables that can be measured 
#### Sparse data
- This sparsity is important. We can use it to our advantage: More efficient storage;Faster computation.
- But we have to use appropriate data structures. Sparse vectors. Typically implemented with hash maps (fast random insertion) or
parallel sorted arrays (slow random insertion but faster reads) 
### spaces, distances and similarity
#### Key terminology
featurevector: a mathematical vector
- just a list of (usually Real) numbers
- has a fixed number of elements in it. The number of elements is the dimensionality of the vector.
- represents a point in a featurespace or equally a direction in the featurespace 
- the dimensionality of a featurespace is the dimensionality of every vector within it. vectors of differing dimensionality can’t exist in the same feature space.
#### Distance and similarity
Feature extractors are often defined so that they produce vectors that are close together for similar inputs. Closeness of two vectors can be computed in the feature space by measuring a distance between the vectors.
- Euclidean distance(L2 distance)
- L1 distance (aka Taxicab/Manhattan). L1 distance is computed along paths parallel to the axes of the space
- Lp distances. Generalisation of the L1 and L2 distances to higher orders
- Cosine Similarity. Cosine similarity measures the cosine of the angle between two vectors.  It is not a distance!  Useful if you don’t care about the relative length of the vectors
#### Measuring user similarity
- Euclidean Similarity. 
- Pearson Correlation. An alternative measure of similarity is to compute the correlation of the users based on the ratings they share. Pearson’s correlation is the standard measure of dependence between two r.v’s. 
#### Important Aside: Grade inﬂation
Users are notoriously bad at giving consistent absolute ratings.
- two users might agree that they both enjoyed a ﬁlm, but one might give it a 4 and the other a 5.
- Pearson correlation corrects for this automatically, but the Euclidean similarity doesn’t
- Data normalisation and mean centring can overcome this.
    - data standardisation
#### User-based Filtering
- Rating and Ranking the critics
    - We now have a set of measures for computing the similarity between users. 
    - Can use this to produce a ranked list of the best matches (most similar users) to a target user. When computing the ranked list, might only want to consider a subset of users. e.g. those who rated a particular item.
- Recommending Items
Now we know how to ﬁnd similar users, how can we recommend items? 
- Predict the rating, *r<sub>u,i</sub>*, of an item *i* by user *u* as an aggregation of the ratings of item *i* by users similar to *u*: <img style="vertical-align:middle" src="http://latex.codecogs.com/svg.latex?\small r_{u,i} = \mathrm{aggr}_{\hat u \in U}(r_{\hat u, i})"/>, where *U* is the set *N* of top users most similar to *u* that rated item *i*.
- Possible aggregation functions: Weight the scores of each item each similar user has rated and combine into a score for each item.
	-  Problem: can’t just add them together - items that have more ratings would always have an advantage. Need to normalise by the sum of ratings.
- Problems with user based ﬁltering
	- User-based ﬁltering relies on computing the similarity against every user. With millions of users this might be a problem! Computationally hard. 
	- If there are thousands of products there might be little overlap between users… 
#### Item based collaborative ﬁltering
Designed to work-around problems of user based ﬁltering. based on the idea that comparisons between items will not change as frequently as comparisons between users. 
- Steps:
	- Precompute the most similar items for each item and store them 
	-  To make a recommendation for a user, look at their top-rated items and aggregate items similar to those from the precomputed item similarities. 
The precomputed item similarities will obviously change with new ratings, but they will do so slowly. 
#### Tradeoffs between user-based and item-based ﬁltering 
- User-based ﬁltering is easier to implement & doesn’t have the overhead of maintaining the item-item comparisons 
- User-based ﬁltering also deals better with datasets that frequently change 
- For small, relatively dense datasets both user-based and item-based ﬁltering perform equally well
- For large, sparse datasets item-based ﬁltering tends to work better
