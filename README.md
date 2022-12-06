# ISE_540_FinalProject

## label_model_new.ipynb
This notebook shows the workflow of choosing the best model to generate "reason matrix". We use Logistic Regression, Random Forest, SVM, SGD classifier and naive bayes classifier with default hyperparameters to predict each reason. This code just shows the workflow of deciding the best model used to predict if_useful tag. But the workflow of all these 10+ features should be nearly the same. 

## label_rest.ipynb
After selecting the best model to predict each reason, we should label the rest of this dataset with these predictors. Here is an example of the extrapolation of if_useful feature.

## score_prediction_final.ipynb
This notebook shows how to select the best model to predict the score of a review. We tried SGDClassifier, RandomForestClassifier and VotingRegression which combine SGD and RF together (and full-connected Neural Networks in score_prediction.ipynb, but the result if poor and there is not enough time for tuning, so we give up this method).
