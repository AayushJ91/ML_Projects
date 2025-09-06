* This algorithm takes probability into account
* First it calculates the probability of each class based on training dataset
* Next, for each feature, the algorithm calculates the likelihood. This is the conditional probability of a specific feature value occurring, given a particular class.
* For a new, unclassified data point, the algorithm uses Bayes' theorem to find the probability of it belonging to each class. The goal is to find the class with the highest probability. It will find P(C|x1,x2,x3,.....,xn)
* P(C|xi) means probability of C given that xi has ocurred
* Assumes that features are not related
* Mostly used for text related datasets
*[[TFI-DF Vectorizer]]
[[Vectorizer]]
#### PROS:
* Very fast to train and predict.
* Works surprisingly well in high-dimensional spaces (like text).
* Requires small training data.
* Handles multiple classes naturally.
#### CONS:
* Assumes feature independence, which is often unrealistic.
* Struggles with numerical data unless discretized.
* Zero probability problem (if a feature/class combination never occurs → needs smoothing).