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
