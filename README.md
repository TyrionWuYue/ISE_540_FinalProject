# ISE_540_FinalProject

## Problem Statement
In the post-epidemic era, people’s entertainment has migrated online, and thus players’ reviews become more important to game companies. Player churning and revenue drop are also essential research topics for the gaming industry. In order to figure out the causes, the research teams in game companies frequently designed and delivered online questionnaires, and conducted interviews to manually summarize the product-specific features closely related to players’ experience. However, not only research teams can’t measure the importance hierarchy for various reasons, but also they lack quantified metrics to monitor players’ experience before potential problems emerge or after the problems are fixed. In order to save the costs of game companies on the research side, we wish to extract information directly from players’ reviews and train NLP models to measure the contribution of each reason to the game’s rating.

## Description and Solution
We focused on Disney Emoji Blitz, a mobile match-3 game, and took 5 steps to complete the project. In the first step, we collected game reviews between  ‘2016-04’ and ‘2022-10’, from Google Play and Apple App Store and preprocessed the text columns, resulting in 163,658 reviews. In the second step, we explored fourteen game-specific functions closely related to players’ experience using K-means text clustering. In the third step, we labeled the reviews with ‘if_useful’ and other fourteen reasons, and used ‘+1’, ‘-1’ to represent sentiment. In the fourth step, we constructed fourteen classifiers to categorize the reviews into reasons related. In the last step, we trained a rating predictor based on the matrix [ # reviews * # reasons] and visualized the contributions of each reason.

We ended up with fourteen reasons closely related to players’ experience, including ‘mechanism’, ‘crash’, ‘data loss’, ‘money’ and others. Most of the clusters are topic-centered, instead of messy, and the reasons are examined by manual reading as feasibility. Besides, when we construct fourteen classifiers for each reason, the classification metrics, like accuracy, are all above the baseline. For instance, our champion model classifying ‘If_useful’ is the ‘Random Forest’ algorithm with default parameters, which has the highest accuracy 0.83 and over the baseline 0.5. Lastly, when we tested the predictor on out-of-sample dataset, we achieved 0.72 accuracy on rating prediction. 



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
