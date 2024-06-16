### Unit 2.2: Cluster Analysis – Types of Data, Partitioning Methods, Hierarchical Methods

#### 2.2.1 Introduction to Cluster Analysis

**Cluster Analysis** (or clustering) is an unsupervised learning technique used to group a set of objects into clusters, such that objects within a cluster are more similar to each other than to those in other clusters. This technique helps in understanding the natural grouping or structure in data.

**Key Concepts**:
- **Clusters**: Groups of similar objects.
- **Similarity/Dissimilarity Measure**: Metric used to quantify how similar or different objects are (e.g., Euclidean distance, Manhattan distance).

#### 2.2.2 Types of Data in Cluster Analysis

Different types of data require different clustering approaches:

1. **Numerical Data**: Continuous data values that can be ordered and measured (e.g., height, weight).
2. **Categorical Data**: Discrete data values that represent categories or classes (e.g., gender, occupation).
3. **Binary Data**: Data with only two possible values (e.g., yes/no, true/false).
4. **Mixed Data**: Data that contains both numerical and categorical attributes.

#### 2.2.3 Partitioning Methods

**Partitioning Methods** divide the data set into a set of disjoint clusters, typically aiming to optimize a specific criterion (e.g., minimizing the within-cluster sum of squares). Common partitioning algorithms include:

**1. k-Means Clustering**:
   - **Concept**: Partitions data into k clusters by assigning each data point to the cluster with the nearest mean.
   - **Algorithm**:
     1. Initialize k centroids randomly.
     2. Assign each data point to the nearest centroid.
     3. Recompute the centroids as the mean of all points in each cluster.
     4. Repeat steps 2 and 3 until convergence.
   - **Advantages**: Simple, efficient for large datasets.
   - **Disadvantages**: Assumes spherical clusters, sensitive to initialization.

**2. k-Medoids (PAM - Partitioning Around Medoids)**:
   - **Concept**: Similar to k-Means but uses actual data points (medoids) as cluster centers.
   - **Algorithm**:
     1. Initialize k medoids randomly.
     2. Assign each data point to the nearest medoid.
     3. Update medoids by selecting the most centrally located point in each cluster.
     4. Repeat steps 2 and 3 until convergence.
   - **Advantages**: More robust to noise and outliers compared to k-Means.
   - **Disadvantages**: More computationally intensive than k-Means.

**3. CLARA (Clustering Large Applications)**:
   - **Concept**: An extension of k-Medoids for large datasets.
   - **Algorithm**:
     1. Select a random sample from the dataset.
     2. Apply k-Medoids to the sample to find k medoids.
     3. Assign all data points in the original dataset to the nearest medoid.
     4. Repeat the process with different samples and choose the best clustering based on a chosen criterion.
   - **Advantages**: Handles large datasets efficiently.
   - **Disadvantages**: Quality depends on the sampling process.

#### 2.2.4 Hierarchical Methods

**Hierarchical Clustering** builds a tree-like structure (dendrogram) that represents the nested grouping of objects. There are two main types of hierarchical clustering: agglomerative and divisive.

**1. Agglomerative Hierarchical Clustering (AHC)**:
   - **Concept**: Bottom-up approach where each data point starts as its own cluster and pairs of clusters are merged iteratively.
   - **Algorithm**:
     1. Start with each data point as a single cluster.
     2. Compute a distance matrix for all clusters.
     3. Merge the closest pair of clusters.
     4. Update the distance matrix.
     5. Repeat steps 3 and 4 until only one cluster remains.
   - **Linkage Criteria**:
     - **Single Linkage**: Distance between the closest points of two clusters.
     - **Complete Linkage**: Distance between the farthest points of two clusters.
     - **Average Linkage**: Average distance between all pairs of points in two clusters.
   - **Advantages**: Does not require the number of clusters to be specified in advance.
   - **Disadvantages**: Computationally intensive, sensitive to noise and outliers.

**2. Divisive Hierarchical Clustering (DHC)**:
   - **Concept**: Top-down approach where all data points start in a single cluster, and splits are performed recursively.
   - **Algorithm**:
     1. Start with all data points in one cluster.
     2. Recursively split the cluster into two sub-clusters.
     3. Continue splitting until each cluster contains a single data point.
   - **Advantages**: More efficient for some datasets compared to agglomerative methods.
   - **Disadvantages**: Computationally intensive, and the initial split can significantly affect the results.

#### 2.2.5 Distance and Similarity Measures

**1. Euclidean Distance**:
   - Measures the straight-line distance between two points in Euclidean space.
   - \[
   d(x, y) = \sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}
   \]

**2. Manhattan Distance**:
   - Measures the distance between two points along the axes at right angles.
   - \[
   d(x, y) = \sum_{i=1}^{n} |x_i - y_i|
   \]

**3. Cosine Similarity**:
   - Measures the cosine of the angle between two vectors.
   - \[
   \text{cosine\_similarity}(x, y) = \frac{x \cdot y}{||x|| \cdot ||y||}
   \]

**4. Jaccard Index**:
   - Measures the similarity between two sets.
   - \[
   J(A, B) = \frac{|A \cap B|}{|A \cup B|}
   \]

#### 2.2.6 Evaluating Clustering Results

**1. Internal Evaluation Metrics**:
   - **Silhouette Score**: Measures how similar a data point is to its own cluster compared to other clusters.
     \[
     s(i) = \frac{b(i) - a(i)}{\max(a(i), b(i))}
     \]
     where \( a(i) \) is the average distance to all points in the same cluster and \( b(i) \) is the average distance to all points in the nearest cluster.
   - **Dunn Index**: Ratio of the minimum inter-cluster distance to the maximum intra-cluster distance.

**2. External Evaluation Metrics**:
   - **Rand Index**: Measures the similarity between two data clusterings by considering all pairs of samples and counting pairs that are either assigned to the same or different clusters in both clusterings.
   - **Adjusted Rand Index**: Adjusts the Rand Index for the chance grouping of elements.

#### Practical Applications

**1. Market Segmentation**:
   - Grouping customers based on purchasing behavior to target marketing efforts.
   - Example: A retail company segments customers into different groups based on buying patterns to design personalized marketing campaigns.

**2. Image Segmentation**:
   - Dividing an image into segments to simplify its analysis.
   - Example: Medical imaging where different tissues are segmented for analysis.

**3. Document Clustering**:
   - Organizing documents into clusters based on content similarity.
   - Example: Grouping news articles into different categories such as sports, politics, and entertainment.

**4. Anomaly Detection**:
   - Identifying unusual patterns that do not conform to expected behavior.
   - Example: Detecting fraudulent transactions in banking by identifying transactions that deviate from normal patterns.

### References

- “Data Mining: Concepts and Techniques” by Jiawei Han, Micheline Kamber, and Jian Pei.
- “Introduction to Data Mining” by Pang-Ning Tan, Michael Steinbach, and Vipin Kumar.
- “Pattern Recognition and Machine Learning” by Christopher Bishop.
- Research articles and case studies on practical applications of clustering techniques.

---

This detailed material for Unit 2.2 should provide a comprehensive understanding of cluster analysis, including types of data, partitioning methods, hierarchical methods, evaluation metrics, and practical applications.
