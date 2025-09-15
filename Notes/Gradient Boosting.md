* A type of [[Ensemble Learning]]
* Here many of the sequential decision trees are used
* At first we will take the parameters(features, Xi) and the target(y) and a base model - could be anything. 
* we will take the prediction of base model(it is avg of target in most cases) and find the difference with the original targets
* These differences are termed as Ri, now we have R1
* Now we will make a decsion tree with inputs as Xi and R1 and it will predict R1 [[Decision Tree]]
* Then the output of decision tree will be used and actual predictions will be calculated
* it will be calculated using : base model output + Learning rate of respective tree * predicted Ri
* This term I am naming as yi
* Then the difference between yi and target will be calculated and
* the new tree will be trained on this difference
* And this will go on for n times (by default 100)
* The basic formula for gradient boosting is = summ`[alpha_i*hi(x)]` from 0 to n where alpha_i belongs to [0,1]
* The hi(x) function are the functions for algorithms for different decision trees and h0(x) is the base model
* for classification we take the negative gradient of loss function
* for successive trees the input will be the original attributes and the negative gradient of loss function with respect to the predictions
* This negative gradient will tell us to for the different classes to go towards them or away from them
[[Variance and Bias]]