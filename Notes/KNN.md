* It makes decison on the basis of nearest neigbours
* Here n points are selected and the distance of the new point from these n points is calculated
* Then the points are arranged based on the distance from the new point
* These points are then matched with their respective classes(groups)
* The classes where points having least distance is predicted as the class of new points
* It has no training phase. Model finds the distance of given point from the stored train_X data
#### PROS:
* Useful for small and medium dataset where the boundaries are irregular.
* Simple for understanding.
#### CONS:
* Since it computes distances, the time will be large for big datasets
* Choice of k and distance metric heavily affects performance.
* Sensitive to irrelevant features and scale (needs normalization)