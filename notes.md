# General Notes

## Normalization:
* Changing the scale of the data points into small fixed ranges
* A dataset containg large datapoints like - 1000000, 5354311 after normalization it will be in small ranges and easy for calculations
* Useful for models like KNN where it needs to deal with numbers

## Regularization:
* In easy terms it sets the hyperparameter(self.theta) of that feature with very large influence(large powers in the relationship)
* for example - if a dataset has relation of 2 features as x1 + x2**5 and the values for both features are 100 then the value for 2nd term (i.e. x2) will become 10000000000 and the value of x1 will be ignored
* Thus to solve this we will set the coeficient of x2 term small like 0.000008 so the new relation will become - x1 + 0.000008x2**5
* Used for models like linear regression and logistic regression which are based on a equartion for a decision boundary
* The cost function will be given as : Cost = Loss + lambda(sum of squares of the present hyperparameter of each of feature)

## Logistic Regression: 
* Uses sigmoid function for classification
* The input of sigmoid function is normal regression function
* ![image-2.png](attachment:image-2.png)
* Uses a linear decision boundary.
### PROS:
* Easy to implement and understand.
* Good for dataset that shows linear relation
* Less prone to overfitting
### CONS:
* Assumes linear boundary
* Sensitive to outliers

## KNN:
* It makes decison on the basis of nearest neigbours
* Here n points are selected and the distance of the new point from these n points is calculated
* Then the points are arranged based on the distance from the new point
* These points are then matched with their respective classes(groups)
* The classes where points having least distance is predicted as the class of new points
* It has no training phase. Model finds the distance of given point from the stored train_X data
### PROS:
* Useful for small and medium dataset where the boundaries are irregular.
* Simple for understanding.
### CONS:
* Since it computes distances, the time will be large for big datasets
* Choice of k and distance metric heavily affects performance.
* Sensitive to irrelevant features and scale (needs normalization)

## Decsion Tree:
* This algosrithm makes the decision based on the tree nodes and leaf nodes
* It takes the targets and different features one-by-one
* Then it classifies the target wrt each target
* Followed by gini impurity : 1 - (probability that it will be class i based on the selected feature)**2; i = (0, number of classes)
* Now the feature having the least gini impurity will be taken as the primary node
* Followed by the bifurcation based on the given feature and finding the impurities for the each feature
### PROS:
* Easy to visualize and interpret.
* Handles numerical + categorical data.
* Captures non-linear relationships.
* No need for feature scaling.
### CONS:
* Prone to overfitting (unless pruned).
* Small changes in data can change the tree (high variance).
* Greedy splitting → not always optimal.

## Naive Bayes: (Multinomial)
* This algorithm takes probability into account
* First it calculates the probability of each class based on training dataset
* Next, for each feature, the algorithm calculates the likelihood. This is the conditional probability of a specific feature value occurring, given a particular class.
* For a new, unclassified data point, the algorithm uses Bayes' theorem to find the probability of it belonging to each class. The goal is to find the class with the highest probability. It will find P(C|x1,x2,x3,.....,xn)
* P(C|xi) means probability of C given that xi has ocurred
* Assumes that features are not related
* Mostly used for text related datasets
### PROS:
* Very fast to train and predict.
* Works surprisingly well in high-dimensional spaces (like text).
* Requires small training data.
* Handles multiple classes naturally.
### CONS:
* Assumes feature independence, which is often unrealistic.
* Struggles with numerical data unless discretized.
* Zero probability problem (if a feature/class combination never occurs → needs smoothing).

## SVM (Supported Vector Machine)
* This model creates

## Different types of scalers

### Standard Scaler
* Uses mean and standard deviation for the scaling
* It does not deals with outliers as the outliers bring the std and mean towards them

### MinMax Scaler
* Uses the min and max values of that feature(column)
* It brings the datapoints between 0-1
* Here the outliers streches the difference (max - min) and brings most values to 0

## Confusion Matrix
* Rows depict the predicted (output) of our model and columns are the actual outcomes
* True Positive - model predicted positive and the predictions are true (match with the actual outcome). In the top left
* True Negative - model predicted negative and the predictions are true (match with the actual outcome). In the bottom right
* False Negatives - model predicted negative and the predictions are false (does'nt match with the actual outcome). In the bottom left
* False Positive - model predicted positive and the predictions are false (does'nt match with the actual outcome). In the top right
* in confusion matrix having shape more than 2X2 all the diagnol elements are treated as true values

### Senstitivity:-
* True Positives / (True Positives + False Negatives)
* It gives us a number which shows us how much predicted outcome are correctly identified as positive
### Specificity:-
* True Negatives / (True Negatives + False Positives)
* It tells us how much predicted outcome are correctly identified as negative
### Accuracy:-
correct predictions / total predictions
### Precision:-
True positive / total positive predictions = TP / (TP + FP)
* It tells how much positive predictions are true
* predictions is the base line
### Recall:-
True Positive / actual true = TP / (TP + FN)
* It tells how much predictions are true out of how much are actualy true
* actual truth is the base line
### F1 score:-
2*(precision*recall) / (precision + recall)
* Harmonic mean between precision and recall