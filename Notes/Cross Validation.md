* In CV, the training dataset is equally divided into k different datasets
* Out of which one of them is considered as validation set
* 'Note': the test dataset is different and is not included here
* During cross validation there are k number of iterations
* In each iteration the validation dataset gets changed and is used to test the remaining training dataset
* We can set the number of folds (k). for k = every sample in training data then it is called "Leave One Out CV"
* After fiting model with inner training dataset we test it with validation test
* This is done k times and for every time we get a score called Cross Validation Score for that iteration
*[[Classification Models]]
