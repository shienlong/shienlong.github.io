# Dealing with Unbalanced Data
## Quick Links
[Shirin's Playground](https://shiring.github.io/machine_learning/2017/04/02/unbalanced)

## Key Takeaway
+ Should not simply over- or under- sample
+ Need to account for cross-validation and perform over- or under- sampling on each fold independently to get honest estimate of 
model performance.

## Undersampling
+ Randomly select samples from class with more instances to match number of samples coming from each class.
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
