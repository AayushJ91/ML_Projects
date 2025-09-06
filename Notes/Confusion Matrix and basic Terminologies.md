* Rows depict the predicted (output) of our model and columns are the actual outcomes
* True Positive - model predicted positive and the predictions are true (matched with the actual outcome). In the top left
* True Negative - model predicted negative and the predictions are true (matched with the actual outcome). In the bottom right
* False Negatives - model predicted negative and the predictions are false (does'nt matched with the actual outcome). In the bottom left
* False Positive - model predicted positive and the predictions are false (does'nt matched with the actual outcome). In the top right
* in confusion matrix having shape more than 2X2 all the diagnol elements are treated as true values

#### Sensitivity:-
* True Positives / (True Positives + False Negatives)
* It gives us a number which shows us out of actual true results how many are predicted true
#### Specificity**:-
* True Negatives / (True Negatives + False Positives)
* It tells us how much out of actual negative result how many our model predicted as negative
#### Accuracy**:-
correct predictions / total predictions
#### Precision**:-
True positive / total positive predictions = TP / (TP + FP)
* It tells how much positive predictions are true
* predictions is the base line
* Of all the items I predicted were positive, how many were actually positive?
#### Recall**:-
True Positive / actual true = TP / (TP + FN)
* It tells how much predictions are true out of how much are actualy true
* actual truth is the base line
* Of all the items that were actually positive, how many did I correctly identify?
#### F1 score**:-
2*(precision*recall) / (precision + recall)
* Harmonic mean between precision and recall