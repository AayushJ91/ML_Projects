## Supervised Classification Learning

### Logistic Regression: 
* Uses sigmoid function for classification
* The input of sigmoid function is normal regression function
* ![image-2.png](attachment:image-2.png)

### KNN:
* It makes decison on the basis of nearest neigbours
* Here n points are selected and the distance of the new point from these n points is calculated
* Then the points are arranged based on the distance from the new point
* These points are then matched with their respective classes(groups)
* The classes where points having least distance is predicted as the class of new points

### Decsion Tree:
* This algosrithm makes the decision based on the tree nodes and leaf nodes
* It takes the targets and different features one-by-one
* Then it classifies the target wrt each target
* Followed by gini impurity : 1 - (probability that it will be class i based on the selected feature)**2; i = (0, number of classes)
* Now the feature having the least gini impurity will be taken as the primary node
* Followed by the bifurcation based on the given feature and finding the impurities for the each feature

### Naive Bayes: (Multinomial)
* This algorithm takes probability into account
* First it calculates the probability of each class based on training dataset
* Next, for each feature, the algorithm calculates the likelihood. This is the conditional probability of a specific feature value occurring, given a particular class.
* For a new, unclassified data point, the algorithm uses Bayes' theorem to find the probability of it belonging to each class. The goal is to find the class with the highest probability. It will find P(C|x1,x2,x3,.....,xn)
* P(C|xi) means probability of C given that xi has ocurred