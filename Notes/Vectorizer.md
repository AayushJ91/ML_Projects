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