# ISE_540_FinalProject

## score_prediction.ipynb
This notebook shows the workflow of choosing the best model to generate "reason matrix". The code just shows the workflow of deciding the best model used to predict if_useful tag. But the workflow of all these 10+ features should be nearly the same.

## score_prediction_final.ipynb
This notebook shows how to select the best model to predict the score of a review. We tried SGDClassifier, RandomForestClassifier and VotingRegression which combine SGD and RF together (and full-connected Neural Networks in score_prediction.ipynb, but the result if poor and there is not enough time for tuning, so we give up this method).
