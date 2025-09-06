* A type of [[Ensemble Learning]]
* for the bagging the most primary model is Random Forest Classifier.
* It consists of many trees therefore called Forest.
* It itself breaks the data into several sub samples and apply the decision trees
* [[Decision Tree]]
* n_estimators - number of trees. default = 100
* criterion - The function to measure the quality of a split. default = "gini"
* max_depth - The maximum depth of the tree. If None, then nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples. default = None
* The default values for the parameters controlling the size of the trees (e.g. max_depth, min_samples_leaf, etc.) lead to fully grown and unpruned trees which can potentially be very large on some data sets.

[[Variance and Bias]]