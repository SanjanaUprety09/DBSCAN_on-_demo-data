DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

DBSCAN is a popular unsupervised clustering algorithm that groups together data points that are closely packed and marks points that lie alone in low-density regions as outliers. It is especially useful for datasets with irregular shapes and noise.

Key Concepts in DBSCAN
1. Parameters

DBSCAN uses two main parameters:

ε (epsilon):
The maximum distance between two points for them to be considered neighbors.

MinPts (Minimum Points):
The minimum number of points required to form a dense region (including the point itself).

2. Types of Points in DBSCAN
a. Core Points

A point is a core point if:

It has at least MinPts points within distance ε.

Core points are the central elements of clusters; they lie in dense regions.

b. Border Points

A point is a border point if:

It has fewer than MinPts points within ε,

But it lies within the neighborhood of a core point.

Border points belong to a cluster but are not dense enough to initiate one.

c. Noise (Outlier) Points

A point is a noise point if:

It is neither a core point nor a border point.

Noise points lie in low-density regions and do not belong to any cluster.

3. Density Concepts
a. ε-Neighborhood

The set of all points within distance ε of a point.

b. Directly Density-Reachable

A point P is directly density-reachable from Q if:

Q is a core point, and

P lies in Q’s ε-neighborhood.

This relationship is not symmetric because P may not be a core point.

c. Density-Reachable

A point P is density-reachable from Q if:

There exists a chain of points P₁, P₂, …, Pₙ

Where each point is directly density-reachable from the previous one.

This relationship is transitive but also not symmetric.

d. Density-Connected

Two points P and Q are density-connected if:

There exists a point O such that both P and Q are density-reachable from O.

This relationship is symmetric, which helps DBSCAN form clusters.



4. How DBSCAN Forms Clusters

Pick an unvisited point.

If the point is a core point, grow a cluster by collecting all points that are density-reachable.

Border points are added to the cluster but do not expand it.

Points that are not density-reachable from any core point are marked as noise.

Continue until all points are visited.

5. Advantages of DBSCAN

Can find clusters of arbitrary shape.

Robust to noise and outliers.

Does not require specifying the number of clusters beforehand.

6. Limitations

Sensitive to the choice of ε and MinPts.

Struggles when cluster densities vary greatly.

Not ideal for high-dimensional data due to distance issues.






