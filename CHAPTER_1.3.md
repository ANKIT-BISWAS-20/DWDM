### Unit 1.3: Mining Frequent Patterns, Associations, and Correlations

#### 1.3.1 Introduction to Frequent Pattern Mining

**Frequent Pattern Mining** is the process of finding recurring relationships or patterns in a dataset. These patterns are significant because they reveal insights into the underlying structure of the data, such as associations, sequences, and correlations.

**Key Concepts**:
- **Frequent Patterns**: Patterns that appear frequently in a dataset. These can include itemsets, subsequences, or substructures.
- **Support**: The frequency or occurrence of a pattern within the dataset. For an itemset, it's the proportion of transactions in which the itemset appears.
- **Confidence**: A measure of the reliability of an association rule. It indicates the likelihood of the consequent occurring when the antecedent is present.

#### 1.3.2 Association Rule Mining

**Association Rule Mining** identifies interesting relationships between variables in large databases. It’s commonly used in market basket analysis to understand product purchasing patterns.

**Components of Association Rules**:
- **Antecedent (LHS)**: The if part of the rule (e.g., {Bread}).
- **Consequent (RHS)**: The then part of the rule (e.g., {Butter}).
- **Rule**: An implication expression of the form X → Y, where X and Y are disjoint itemsets.

**Measures**:
- **Support (s)**: \( \text{Support}(X \rightarrow Y) = \frac{\text{Number of transactions containing } X \cup Y}{\text{Total number of transactions}} \)
- **Confidence (c)**: \( \text{Confidence}(X \rightarrow Y) = \frac{\text{Support}(X \cup Y)}{\text{Support}(X)} \)
- **Lift**: \( \text{Lift}(X \rightarrow Y) = \frac{\text{Confidence}(X \rightarrow Y)}{\text{Support}(Y)} \)

**Example**:
- If 100 out of 1000 transactions contain both Bread and Butter, the support is 10%.
- If 80 of those 100 transactions that contain Bread also contain Butter, the confidence is 80%.

#### 1.3.3 Algorithms for Mining Frequent Patterns

**1. Apriori Algorithm**:
   - **Apriori Principle**: If an itemset is frequent, then all of its subsets must also be frequent.
   - **Steps**:
     1. Generate candidate itemsets of length k from frequent itemsets of length k-1.
     2. Prune candidate itemsets containing infrequent subsets.
     3. Count the support of each candidate and select those meeting the minimum support threshold.
     4. Repeat until no more frequent itemsets are found.

   - **Advantages**: Simple and easy to implement.
   - **Disadvantages**: Can be computationally expensive due to multiple database scans.

**2. FP-Growth Algorithm**:
   - **FP-Tree**: A compact data structure that represents frequent patterns.
   - **Steps**:
     1. Construct the FP-tree by reading the dataset and accumulating item counts.
     2. Recursively extract frequent itemsets from the FP-tree.

   - **Advantages**: More efficient than Apriori, especially for large datasets.
   - **Disadvantages**: More complex implementation and higher memory usage.

#### 1.3.4 Sequential Pattern Mining

**Sequential Pattern Mining** involves finding regular sequences of events or actions over time. This is useful in applications like customer purchase sequences, web clickstreams, and DNA sequencing.

**Concepts**:
- **Sequence**: An ordered list of events or items.
- **Support**: The proportion of sequences in the database that contain a particular subsequence.

**Algorithms**:
- **AprioriAll**: An extension of the Apriori algorithm for sequential pattern mining.
  - Generates candidate sequences by joining frequent subsequences and pruning those with infrequent subsequences.
- **GSP (Generalized Sequential Pattern)**: Similar to AprioriAll but includes additional constraints like time gaps and item constraints.
- **PrefixSpan (Prefix-Projected Sequential Pattern Mining)**: Uses pattern-growth approach, where it recursively projects the database based on prefix sequences and mines the projected databases.

#### 1.3.5 Correlation Analysis

**Correlation Analysis** measures the statistical relationship between two variables, indicating whether an increase or decrease in one variable corresponds to an increase or decrease in another.

**Measures**:
- **Pearson Correlation Coefficient (r)**: Measures linear correlation between two variables.
  - \( r = \frac{n(\Sigma xy) - (\Sigma x)(\Sigma y)}{\sqrt{[n \Sigma x^2 - (\Sigma x)^2][n \Sigma y^2 - (\Sigma y)^2]}} \)
  - Values range from -1 (perfect negative correlation) to +1 (perfect positive correlation), with 0 indicating no correlation.
- **Spearman's Rank Correlation**: Measures the correlation between ranked variables, useful for non-parametric data.

#### 1.3.6 Scalable Methods for Frequent Pattern Mining

**Challenges**:
- Handling large datasets efficiently.
- Reducing computational complexity and memory usage.

**Approaches**:
- **Sampling**: Analyzing a representative subset of the data to infer patterns.
- **Parallel and Distributed Computing**: Using multiple processors or machines to distribute the computation, e.g., MapReduce.
- **Incremental Mining**: Updating frequent patterns as new data arrives without reprocessing the entire dataset.

#### Practical Applications

**1. Market Basket Analysis**:
   - Identifying product bundles, optimizing store layouts, and improving cross-selling strategies.
   - Example: A retailer finds that customers who buy diapers often also buy beer, leading to promotional strategies that place these items nearby.

**2. Customer Segmentation**:
   - Grouping customers based on purchasing behavior to tailor marketing campaigns.
   - Example: A telecom company segments customers into different usage patterns to offer customized plans.

**3. Fraud Detection**:
   - Detecting unusual patterns indicative of fraudulent activity.
   - Example: Credit card companies use pattern mining to identify anomalous transactions that deviate from typical spending behavior.

**4. Bioinformatics**:
   - Analyzing DNA sequences to find genetic markers associated with diseases.
   - Example: Identifying frequent subsequences in DNA data to predict disease susceptibility.

### References

- “Data Mining: Concepts and Techniques” by Jiawei Han, Micheline Kamber, and Jian Pei.
- “Introduction to Data Mining” by Pang-Ning Tan, Michael Steinbach, and Vipin Kumar.
- “Mining of Massive Datasets” by Jure Leskovec, Anand Rajaraman, and Jeffrey Ullman.
- Research articles and case studies on practical applications of frequent pattern mining.

---

This detailed material for Unit 1.3 should provide a comprehensive understanding of frequent pattern mining, association rules, and correlation analysis, including key concepts, algorithms, and practical applications.
