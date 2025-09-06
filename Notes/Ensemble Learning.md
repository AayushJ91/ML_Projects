* Breaking the original dataset into k smaller subsets.
* Applying the same model to all the subsets and get the result
* The subsets are made with replacement resampling method and is called 'Bootstrapping Aggregation' or 'Bagging'
* from that use the prediction that is predicted most number of times
* Meaning the prediction which is predicted most of the time among the subsets
* Random Forest model is an example of Bootstrapping aggregations
* It just not only sample the rows (data samples) but also sample the fetaures
* We can do bagging using various models (SVM, logistic regression etc.)
* When the each underlying model is Random Forest it is called "Bagged Tree"