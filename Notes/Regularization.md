[[Normalization]]
[[Scalers]]
* In easy terms it sets the hyperparameter(self.theta) of that feature with very large influence(large powers in the relationship)
* for example - if a dataset has relation of 2 features as x1 + x2**5 and the values for both features are 100 then the value for 2nd term (i.e. x2) will become 10000000000 and the value of x1 will be ignored
* but by observation there is an influence of x1 also
* Thus to solve this we will set the coeficient of x2 term small like 0.000008 so the new relation will become :- x1 + 0.000008x2**5
* Used for models like linear regression and logistic regression which are based on a equation for a decision boundary
* The cost function will be given as : Cost = Loss + lambda(sum of squares of the present hyperparameter of each of feature)