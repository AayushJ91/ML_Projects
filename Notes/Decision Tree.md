* This algorithm makes the decision based on the tree nodes and leaf nodes
* It takes the targets and different features one-by-one
* Then it classifies the target wrt each target
* Followed by gini impurity : 1 - (probability that it will be class i based on the selected(parent leaf) feature)**2; i = [0, number of classes]
* Total gini impurity of a leaf is the weighted average of Gini Impurities for the Leave impurity
* i.e. it is the product of gini impurity of that leaf with the ratio of instances in that leaf upon the total leaf
* the total gini impurity will be associated with the parent leaf
* Now the feature having the least gini impurity will be taken as the primary node
* Followed by the bifurcation based on the given feature and finding the impurities for the each feature
#### PROS:
* Easy to visualize and interpret.
* Handles numerical + categorical data.
* Captures non-linear relationships.
* No need for feature scaling.
#### CONS:
* Prone to overfitting (unless pruned).
* Small changes in data can change the tree (high variance).
* Greedy splitting → not always optimal.
[[Variance and Bias]]