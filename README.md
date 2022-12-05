# Unsupervised-Learning-Techniques
## Unsupervised leraning techniques in machine learning

Clustering: the goal is to group similar instances together into clusters. This is a great tool for data analysisi, customer segmentation, recommender systems, serach engines, image segmentation, semi supervised learning, dimensionality reduction and more.



Anomaly detection: the objective is to learn what normal data looks like, and use this to detect abnormal instances, suvh as defective items on a production line or a new trend in a time series.


Density estimation: this is the task of estimating the probability density function of the random process that generated the dataset.



## CLustering

There is no univera=sal definition of what a cluster is: it reallydepends on the context ad different algorithms will capture different kinds of clusters.


## K-Means

hard clustering :- assigning each instance to a single cluster

soft clustering :- giving each instance a score per cluster.


### The K-Means algorithms
Suppose you were given the centroids: you could easily label all the instances in the dataset by assigning each of them to the cluster whose centroid id closest.

Conversely, if you were given all the instances labels, you could easily locate all the centroids by computing the mean of intsnaces for each cluster.

The computational complexity of the algorthm is generally linear with regards to the number of the instances m, the number of clusters k and the number of dimensions n.


## Centroid Initialization Methods

K-Means++ :- 

	i) Take one centroid ci chosen uniformly at random from the dataset
	ii) Take a new centroid ci, choosing an instance xi with probability D(Xi)^2 - formula formula
	iii) Repeat tthe previous step until all k centroids have been chosen.

### Accelerated k_means and Mini-Batcg k-means

The kmeans has been accelerated by avoiding many unnecessary distance calculations: this is achieved by exploiting the triangle inequality and keeping track of lower and upper bounds for distances between instances and centroids


### Finding the Optimal Number of Clusters

Inertial Technique :- Elbow rule

Silhoutte :-


### Limits of K-Means

-Its necessary to run the algorithim several times to avoid sub-optimal solutions
-you need to specify the number of clusters
-K-means does not behave very well when the clusters have varying sizes, diferent densitiies, or non spherical shapes.


### Using clustering for image segmentation

Partitioning an image into multiple segments.


In instrance segmentation, all pixels that are part of the same individual object are assigned to the same segment.


### Active learning

This is when  a human expert interacts with the learning algorithm, providing labels when the algorithm needs them

uncertainity sampling:- The models is trained on the labels instances gathered so farm and this models is used to make predictions on all the unlabeled instances.

The instances for which the model is most uncertain must be labeled by the expert

Then you just iterate this process again and again, until the perfromance imporoement stop s being worth the labelling effort.



### DBSCAN
This algorithm defines clusters as continous regions of high density.

- For each instance the algorithm counts how many instances are located within a small distance e (epsilon) from it

- if an instance has at least min_samples instances in its e-neighbourhood then it is considered a core instance.

- all instances in the neigbourhood of a core instance belong to the same cluster

- any instance that is not a core instance and does not have one in its neighbourhood is considered an anomaly.


DBSCAN is a very simple yet powerful algorithm, capable of identifying any number of clusters, of any shape, it is robust to outliers, and it has just two hyperparamters (eps and min-smaples).

However, if the density varies significantly across the clusters, it can be impossible for it to capture all the clusters properly.


### Other Clustering Algorithms
Agglomerative clustering:- A hierachy of clusters is built from the bottom up.


Birch :-This algorithm was designed specifically for very large datasets, and it can be faster than the batch K-means with similar results, as long as the number of features is not too large.


Mean-shift: This algorithm starets by placing a ircle centered on each instance, then for each circle it computes the mean of all the instances located within it, and it shifts the circle so that it is centered on the mean.

Affinity propagation: -This algorithm uses a voting system, where instances vote for similar instances to be their representatives, and once the algorithm converges, each representatives and its voters for a cluster.





## Gaussian Mixtures

This is a probabilisti model that assumes that the instances were generated from a mixture of several gaussian desitributions whose paramters are unknowns


### Other Anomaly Detection and Novelty Detection Algorithms

Fast-MCD This sis an efficient algorithm for outlier detection.

Isolation Forest :- this is an efficient algorithm for outlier detection, especially in hiugh-dimesnional datasets.

Local outlier factor :-It compares densities of instances around a given instance to the density around its neighbours


One-class SVM: This algorithm is better suited for novelty detetiioon.



