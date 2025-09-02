# General Notes

## **Normalization**:
* Changing the scale of the data points into small fixed ranges
* A dataset containg large datapoints like - 1000000, 5354311 after normalization it will be in small ranges and easy for calculations
* Useful for models like KNN where it needs to deal with numbers

## **Regularization**:
* In easy terms it sets the hyperparameter(self.theta) of that feature with very large influence(large powers in the relationship)
* for example - if a dataset has relation of 2 features as x1 + x2**5 and the values for both features are 100 then the value for 2nd term (i.e. x2) will become 10000000000 and the value of x1 will be ignored
* but by observation there is an influence of x1 also
* Thus to solve this we will set the coeficient of x2 term small like 0.000008 so the new relation will become :- x1 + 0.000008x2**5
* Used for models like linear regression and logistic regression which are based on a equation for a decision boundary
* The cost function will be given as : Cost = Loss + lambda(sum of squares of the present hyperparameter of each of feature)

## **Logistic Regression**:
* Uses sigmoid function for classification
* The input of sigmoid function is normal regression function
* ![image-2.png](attachment:image-2.png)
* Uses a linear decision boundary.
### **PROS**:
* Easy to implement and understand.
* Good for dataset that shows linear relation
* Less prone to overfitting
### **CONS**:
* Assumes linear boundary
* Sensitive to outliers

## **KNN**:
* It makes decison on the basis of nearest neigbours
* Here n points are selected and the distance of the new point from these n points is calculated
* Then the points are arranged based on the distance from the new point
* These points are then matched with their respective classes(groups)
* The classes where points having least distance is predicted as the class of new points
* It has no training phase. Model finds the distance of given point from the stored train_X data
### **PROS**:
* Useful for small and medium dataset where the boundaries are irregular.
* Simple for understanding.
### **CONS**:
* Since it computes distances, the time will be large for big datasets
* Choice of k and distance metric heavily affects performance.
* Sensitive to irrelevant features and scale (needs normalization)

## **Decsion Tree**:
* This algorithm makes the decision based on the tree nodes and leaf nodes
* It takes the targets and different features one-by-one
* Then it classifies the target wrt each target
* Followed by gini impurity : 1 - (probability that it will be class i based on the selected(parent leaf) feature)**2; i = [0, number of classes]
* Total gini impurity of a leaf is the weighted average of Gini Impurities for the Leave impurity
* i.e. it is the product of gini impurity of that leaf with the ratio of instances in that leaf upon the total leaf
* the total gini impurity will be associated with the parent leaf
* Now the feature having the least gini impurity will be taken as the primary node
* Followed by the bifurcation based on the given feature and finding the impurities for the each feature
### **PROS**:
* Easy to visualize and interpret.
* Handles numerical + categorical data.
* Captures non-linear relationships.
* No need for feature scaling.
### **CONS**:
* Prone to overfitting (unless pruned).
* Small changes in data can change the tree (high variance).
* Greedy splitting → not always optimal.

## **Naive Bayes: (Multinomial)**
* This algorithm takes probability into account
* First it calculates the probability of each class based on training dataset
* Next, for each feature, the algorithm calculates the likelihood. This is the conditional probability of a specific feature value occurring, given a particular class.
* For a new, unclassified data point, the algorithm uses Bayes' theorem to find the probability of it belonging to each class. The goal is to find the class with the highest probability. It will find P(C|x1,x2,x3,.....,xn)
* P(C|xi) means probability of C given that xi has ocurred
* Assumes that features are not related
* Mostly used for text related datasets
### **PROS**:
* Very fast to train and predict.
* Works surprisingly well in high-dimensional spaces (like text).
* Requires small training data.
* Handles multiple classes naturally.
### **CONS**:
* Assumes feature independence, which is often unrealistic.
* Struggles with numerical data unless discretized.
* Zero probability problem (if a feature/class combination never occurs → needs smoothing).

## **SVM (Supported Vector Machine)**
* This model creates a boundary with margins (margin = the distance between the boundary and the nearest data points from each class.)
* The nearest data points from each class is called Support Vectors
* It is a good model for binary classification as it sets margins and boundaries
* If the classes that cannot be seperated by a straight line we use kernel functions
* Linear seperable dataset also uses linear kernel 
* But for other datasets different kernels can be used - 'rbf, poly, sigmoid'
* With kernel we transform the data into higher dimension and then find a new boundary

## Different types of scalers

### **Standard Scaler**
* Uses mean and standard deviation for the scaling
* It does not deals with outliers as the outliers bring the std and mean towards them

### **MinMax Scaler**
* Uses the min and max values of that feature(column)
* It brings the datapoints between 0-1
* Here the outliers streches the difference (max - min) and brings most values to 0

## **Confusion Matrix**
* Rows depict the predicted (output) of our model and columns are the actual outcomes
* True Positive - model predicted positive and the predictions are true (matched with the actual outcome). In the top left
* True Negative - model predicted negative and the predictions are true (matched with the actual outcome). In the bottom right
* False Negatives - model predicted negative and the predictions are false (does'nt matched with the actual outcome). In the bottom left
* False Positive - model predicted positive and the predictions are false (does'nt matched with the actual outcome). In the top right
* in confusion matrix having shape more than 2X2 all the diagnol elements are treated as true values

### **Senstitivity**:-
* True Positives / (True Positives + False Negatives)
* It gives us a number which shows us out of actual true results how many are predicted true
### **Specificity**:-
* True Negatives / (True Negatives + False Positives)
* It tells us how much out of actual negative result how many our model predicted as negative
### **Accuracy**:-
correct predictions / total predictions
### **Precision**:-
True positive / total positive predictions = TP / (TP + FP)
* It tells how much positive predictions are true
* predictions is the base line
* Of all the items I predicted were positive, how many were actually positive?
### **Recall**:-
True Positive / actual true = TP / (TP + FN)
* It tells how much predictions are true out of how much are actualy true
* actual truth is the base line
* Of all the items that were actually positive, how many did I correctly identify?
### **F1 score**:-
2*(precision*recall) / (precision + recall)
* Harmonic mean between precision and recall

## **Vectorization**
For a dataset containing texts such as spam email dataset we cannot take input as strings.
* So to transform the dataset into numerical form we can use Vectorization 
* Here, vectorization will make a matrix like structure where rows will signify each entry
* and the columns will be some words that occur repeatedly (like free, general, discount) but not the general words (like is, are, the)
* Now, each cell can be of 2 types - either it will show the presence of a specific word in a specific entry 
* or will show the number occurence of that word in specific entry
* After, vectorization we can use various models to get fit to the vectorized dataset
* it is build in sklearn.feature_extraction.text.CountVectorizer
* For training data we will use fit_transform - this will figure out the words and make the matrix by itself
* For testing data we will use only transform - this will transform the testing data to a matrix where the words are from training dataset

## **TfidfVectorizer**
* TF IDF :- Term Frequency - Inverse Document Frequency
* Term Frequency (TF) = ocurance of a particular word in a document / total words of that document
* IDF = log (Total Entries / number of documents where that word is occuring)
* TfIdf = TF*IDF
* Now we will calculate the TF-IDF of each word for each entry

## **Pipelines**
* These are a kind of structures which includes transformation and fiting in one line
* Here the inside things are called the steps and it includes transformation step and then estimators step

## **ROC graph**
* ROC stands for Reciever Operator Characteristics
* It is a graphhical representation of binary classification model for different threshold values
* y-axis shows the True Positive Rate (TPR) in simple words it is sensitivity (recall)
* x-axis shows the False Positive Rate (FPR) which is (1 - Specificity)
* ROC graph summarizes the confusion matrix of different thresholds for a classification task
* for different models of classifications, the model having the large AUC (Area Under Curve) will be a better classifier
* AUC varies between 0 and 1
* False Positive Rate is often replaced by the precision
* For a point in ROC curve the y projection shows the percentage of how many positive predictions are actually true
* and the x projection shows the percentage of how many positive predictions are wrongly predicted

## **Cross-Validation**:
* In CV, the training dataset is equally divided into k different datasets
* Out of which one of them is considered as validation set
* 'Note': the test dataset is different and is not included here
* During cross validation there are k number of iterations
* In each iteration the validation dataset gets changed and is used to test the remaining training dataset
* We can set the number of folds (k). for k = every sample in training data then it is called "Leave One Out CV"
* After fiting model with inner training dataset we test it with validation test
* This is done k times and for every time we get a score called Cross Validation Score for that iteration

## **Ensemble learning**:
* Breaking the original dataset into k smaller subsets.
* Applying the same model to all the subsets and get the result
* The subsets are made with replacement resampling method and is called 'Bootstrapping Aggregation' or 'Bagging'
* from that use the prediction that is predicted most number of times
* Meaning the prediction which is predicted most of the time among the subsets
* Random Forest model is an example of Bootstrapping aggregations
* It just not only sample the rows (data samples) but also sample the fetaures
* We can do bagging using various models (SVM, logistic regression etc.)
* When the each underlying model is Random Forest it is called "Bagged Tree"

## **Random Forest Classifier**:
* for the bagging the most primary model is Random Forest Classifier.
* It consists of many trees therefore called Forest.
* It itself breaks the data into several sub samples and apply the decision trees
* n_estimators - number of trees. default = 100
* criterion - The function to measure the quality of a split. default = "gini"
* max_depth - The maximum depth of the tree. If None, then nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples. default = None
* The default values for the parameters controlling the size of the trees (e.g. max_depth, min_samples_leaf, etc.) lead to fully grown and unpruned trees which can potentially be very large on some data sets.
