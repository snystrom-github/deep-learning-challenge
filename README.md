# deep-learning-challenge
Challenge 21

**ANALYSIS**

**Data Preprocessing and Cleaning**

The first I improved and preprocessed the data by loading the dataset (charity_data.csv) into a pandas DataFrame and displayed the first few rows using head(). I dropped non-beneficial columns “EIN” and “NAME” and removed them from the dataset using the drop() method. Then I used nunique() to determine the number of unique values in each column to see which features were categorical and which could be used for modeling.

**Handling Categorical Features**

After identifying the categorical variables, I performed value counts analysis to spot infrequent categories. I grouped application types with fewer than 500 occurrences into an "Other" category to simplify the feature Similarly, I identified classifications with fewer than 1,000 occurrences and replaced them with "Other". This reduced the number of categories to help the model focus on the more important classifications.

**Data Transformation**

I used the standard technique pd.get_dummies() to convert categorical features into numerical values via one-hot encoding.

**Feature and Target Split**

I separated the data into features (X) and the target variable (y), specifically using the IS_SUCCESSFUL column as the target, then split the data into training and testing sets using train_test_split(), ensuring the training data would be used to train the model while the testing data would be reserved for final evaluation.

**Feature Scaling**

I used StandardScaler to scale the features in the dataset. 

**Neural Network Model Setup**

I defined a Sequential model using TensorFlow/Keras and added a first hidden layer with 8 nodes and a second hidden layer with 5 notes (both with ReLU activation functions), and an output layer with a single neuro with a sigmoid activation function.

**Model Compilation and Training**

I compiled the model with the binary cross-entropy loss and the Adam optimizer, and trained the model for 100 epochs on the scaled training data and monitored its performance.

**Model Evaluation**

Then I used evaluate() on the test set to assess how well the model generalizes to unseen data and provides the loss and accuracy values to judge the model's overall performance.

**Model Evaluation Output**
     Loss: 0.5550
     Accuracy: 0.7258

**Output Interpretation**

1. Accuracy (0.7258 or 72.58%): The model has an accuracy of 72.58% on the test set. This means that approximately 72.58% of the time, the model correctly predicted whether a charity application would be successful or not. This is a fairly decent start, but I would want to aim for higher accuracy if taking this project further.

2. Loss (0.5550): The loss value of 0.5550 (binary cross-entropy loss) indicates how well the model’s predictions align with the true labels. In binary classification, lower loss values represent better model performance, with a value closer to 0 indicating near-perfect predictions, but it suggests there is room for improvement. 

**Potential Future Improvements**

 I could add more complexity to the model with more hidden layers or notes. 
 I could experiment with varying the number of epochs, batch size, and learning rate. 
 I could look at metrics such as Precision, Recall, or F1-score.

