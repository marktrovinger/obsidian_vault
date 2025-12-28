- "Learning with a teacher" (supervised) vs. "Learning without a teacher" (unsupervised)
- Identify patterns, structures and patterns within data
- Cluster analysis identifies where the probability function $Pr(x)$ is locally maximized

### Dimensionality Reduction
- Reduce the number of variables under consideration
- PCA seeks a lower dimensional representation of the data whereas clustering seeks to clarify group structure
- Association Rule Mining, typically found in databases, id patterns, series of "if-then"

### Usefulness 
- Data without labels
- Higher dimensional space


## Cluster Analysis
- Clusters should occur naturally in the data
- Cluster for understanding
- Cluster for utility

### Similarity/Dissimilarity Metrics
- We want:
	- High intra-cluster similarity
	- Low inter-class similarity
- Similarity measure or function
	- distance measure for dissimilarity
	- Dissimilarity matrix

### Partitioning
### K-means
- Keep within-cluster variation low
- Becomes an optimization problem
- Choose good initial centroids

### Hierarchical Clustering
- Dendrogram
	- Tree-like structure that shows the hierarchy of clusters
	- Y-axis is the linkage distance
	- Gives an idea of where the clusters occur
- Doesn't require a number of clusters 
- Types:
	- Uses a proximity matrix
	- Agglomerative
		- Starts with each point as a cluster, glues them together
		- Most common type
	- Divisive
		- Start with one big clump and split
- Problems
	- Computationally expensive
	- Noise sensitivity

## Evaluation
- Hopkins statistic
	- Range (0,1)
	- $H>0.5$, unlikely that there is a statistically significant cluster
- Number of clusters
	- Simple method: $\sqrt\frac{n}{2}$, where $n$ is the number of data points
	- Elbow method: Turning point in a curve
	- Cross-validation: divide into $m$ parts, test on $m-1$ 
- Often there is no external validation
- Unsupervised:
	- Measure without respect to an external source, internal indices
- Supervised:
	- How well does it match some external structure?
	- External indices
- Relative 