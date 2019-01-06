# Clustering using DBSCAN 

#### Dataset:
Data file contains 8580 text records in sparse format.Labels are not provided.

#### AIM:
Assign each text record to identified clusters ranging from 1 to K.

#### Approach:
1)Read records from file in sparse format and store it into CSR matrix.
2)Normalise CSR matrix by Inverse Document Frequency to minimise impact of frequent words.
3)Perform Dimensionality Reduction algorithm SVD to inhibit influence of document length.
4)Using DBSCAN cluster the text document.
5)Evaluate cluster formation using calinski harabaz metrics.

#### DBSCAN Implementation:
Two parameters are to be given to DBSCAN algorithm namely radius(eps) and min points(minpts).

For a given radius and minpts,check if the distance(Euclidean in this case) and minpts fall in the parameter range,if yes than those points are core points and if minpts in the neighbourhood are less than set parameters than they are border points and rest points are noise points.

Create a graph in which core points are connected if they are within eps distance of each other.

Determine connected components in graph.

Assign each border point to connected component with which it is best connected.

Points in each connected component are returned as cluster.


