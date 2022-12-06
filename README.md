# ISE_540_FinalProject

## Datacollection_goo.ipynb
This notebook shows the workflow of data collection of Disney Emoji Blitz's reviews from Google Play.

## ClusterExploration.ipynb
This notebook shows the process of cluster exploration. In order to explore possible features closely related to players' experience and ratings, we updated stopword to remove messy cluster results. After 3rd iteration, the clusters show many game-specific features.

## classification_me_ad.ipynb
This notebook shows the classifiers of 'mechanism' and of 'ad'.

## Label_me_ad.ipynb
This notebook implemented the classifiers of 'mechanism' and of 'ad' to unlabeled reviews. The result will be concatenated with other columns, and be used for score prediction.

## label_model_new.ipynb
This notebook shows the workflow of choosing the best model to generate "reason matrix". We use Logistic Regression, Random Forest, SVM, SGD classifier and naive bayes classifier with default hyperparameters to predict each reason. This code just shows the workflow of deciding the best model used to predict if_useful tag. But the workflow of all these 10+ features should be nearly the same. 

## label_rest.ipynb
After selecting the best model to predict each reason, we should label the rest of this dataset with these predictors. Here is an example of the extrapolation of if_useful feature.

## score_prediction_final.ipynb
This notebook shows how to select the best model to predict the score of a review. We tried SGDClassifier, RandomForestClassifier and VotingRegression which combine SGD and RF together (and full-connected Neural Networks in score_prediction.ipynb, but the result if poor and there is not enough time for tuning, so we give up this method).
