# Data Cleaning and Analysis

## Data Exploration and Preprocessing:

* After loading the credit card transaction dataset, analyze the data, and check for any missing values.
* Visualize the class distribution to observe the class imbalance between normal (non-fraudulent) transactions and fraudulent transactions.

## Handling Class Imbalance:

* Since fraudulent transactions are typically rare compared to normal transactions, the dataset is imbalanced.
* To address this imbalance, a common approach is under-sampling, where a subset of the majority class (normal transactions) is randomly sampled to match the number of instances in the minority class (fraudulent transactions).

## Under-Sampling Process:

* Separate the original dataset into two subsets: one containing normal transactions (non-fraudulent) and the other containing fraudulent transactions.
* Randomly sample a subset from the normal transactions (non-fraudulent) dataset. The size of this subset is set to match the number of fraudulent transactions in the original dataset. This ensures that the new dataset will have an equal number of normal and fraudulent transactions.
* The under-sampled subsets are stored in separate data frames: sampled_normal (sampled normal transactions) and fraud (original fraudulent transactions).

## Concatenation:

* After under-sampling, the code concatenates the two data frames, sampled_normal and fraud, along the rows to create a new data frame ccData_new.
* The resulting ccData_new data frame contains both under-sampled normal transactions and the original fraudulent transactions, forming a balanced dataset with equal representation of both classes.

## Training and Testing Split:

* The ccData_new data frame is then used for model training and testing. The features (independent variables) are stored in X, and the target variable (Class: normal or fraud) is stored in Y.
* The data is split into training and testing sets using the train_test_split function. This ensures that the model is trained on a portion of the data and evaluated on unseen data.


# Models used

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Random Forest

## Logistic Regression:
* Logistic Regression is a simple and interpretable linear classifier commonly used for binary classification tasks.
* The model estimates the probabilities of the target class (fraudulent or non-fraudulent) based on the input features.
* It works well when there is a linear relationship between the features and the target class.
* In the project, the Logistic Regression model is trained using the under-sampled and balanced dataset ccData_new. The training process involves adjusting the model parameters to minimize the logistic loss function.
* The model is evaluated on the test data to calculate accuracy, recall, precision, and F1 score.

### Logistic Regression Metrics

* Accuracy on Test Data: 94.42%
* Recall score on Test Data: 94.41%
* Precision on Test Data: 93.00%
* F1 score on Test Data: 94.42%

## K-Nearest Neighbors (KNN)
* K-Nearest Neighbors is a non-parametric and lazy learning algorithm used for both classification and regression tasks.
* In KNN, each data point is assigned a class based on the majority class of its k-nearest neighbors.
* It is a distance-based algorithm and works well with both linear and non-linear relationships between features and classes.
* In the project, the KNN model is trained using the under-sampled and balanced dataset ccData_new. The training process mainly involves storing the * training data in memory.
* During prediction, the model calculates the distances between the test data and the training data to determine the k-nearest neighbors and assigns the class based on majority voting.
* The model's performance is evaluated on the test data to calculate accuracy, recall, precision, and F1 score.

### KNN Metrics
* Accuracy on Test Data: 94.21%
* Recall score on Test Data: 96.84%
* Precision on Test Data: 92.00%
* F1 score on Test Data: 94.36%

## Random Forest:

* Random Forest is an ensemble learning method that combines multiple decision trees to make predictions.
* It is robust, handles non-linear relationships well, and reduces overfitting compared to a single decision tree.
* Random Forest works by creating multiple decision trees using random subsets of the data and features.
* During prediction, each decision tree votes on the final prediction, and the class with the most votes is chosen as the predicted class.
* In the project, the Random Forest model is trained using the under-sampled and balanced dataset ccData_new. The training process involves building multiple decision trees with bootstrapped subsets of the data and random subsets of the features.
* The model's performance is evaluated on the test data to calculate accuracy, recall, precision, and F1 score.

### Random Forest Metrics

* Accuracy on Test Data: 94.74%
* Recall score on Test Data: 98.91%
* Precision on Test Data: 91.00%
* F1 score on Test Data: 94.79%
