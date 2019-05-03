# Dealing with Unbalanced Data
## Quick Links
[Shirin's Playground](https://shiring.github.io/machine_learning/2017/04/02/unbalanced) - Brief intro with codes
[MarcoAltini](https://www.marcoaltini.com/blog/dealing-with-imbalanced-data-undersampling-oversampling-and-proper-cross-validation) - More details and explanation, some code.
[Alfredo Motta](http://www.alfredo.motta.name/cross-validation-done-wrong/) - Cross validation done wrong.
[My Notes](https://shienlong.github.io/python_notes) - Python notes

## Key Takeaway
+ Classifiers are more sensitive to detecting majority class, less sensitive to minority class.
+ Should not simply over- or under- sample
+ Need to account for cross-validation and perform over- or under- sampling on each fold independently to get honest estimate of 
model performance.

## Undersampling
+ Randomly select samples from class with more instances to match number of samples coming from each class.
+ Sensitivity of model improve
+ Disadvantage:
 + May lose potentially relevant information from left out samples.
 
 ## Oversampling
 + Randomly duplicate samples from the class with fewer instances or generate additional instances based on data available to match
 of samples in each class.
 + Avoid losing information.
 + Disadvantage:
  + Risk of overfitting.
  + More likely get the same samples in training and test dataset.
  + Test data no longer independent from training data.
  + Overestimation of model performance.
  
  ## Cross-Validation
  - Cross validation is a tool to estimate accuracy of algorithm.
  - Involves randomly dividing set of observations into k-groups (or folds) of approx equal size. 
  - First fold treated as validation set. ML algo trained on remaining k-1 folds.
  - MSE (Mean Squared Error) computed on the held out validation fold. 
  - This procedure repeated k times with diff group of observations treated as validation set. 
  - For each iteration, **exclude the sample to use as validation dataset**. Then oversample remaining minority class. Now not using same data for training and validation.
  - Other methods for oversample: SMOTE but does not deal with cross validation.
