# voting-and-stacking-ensemble

There are different types of Ensemble Learning techniques which differ mainly by:

    the type of models used (homogeneous or heterogeneous models), 
    the data sampling (with or without replacement, k-fold, etc.) and 
    the decision function (voting, average, meta model, etc).
    
Therefore, Ensemble Learning techniques can be classified as:
    
    Bagging
    Boosting
    Stacking


In addition to these three main categories, two important variations emerge: 
    
    Voting (which is a complement of Bagging) and 
    Blending (a subtype of Stacking). 

Although Voting and Blending are a complement and a subtype of Bagging and Stacking respectively, these techniques are often found as direct types of Ensemble Learning.


**Stacking:**

Better known as Stacking Generalization, the key is to reduce the generalization error of different generalizers (i.e. ML models). 

The general idea of the Stacking Generalization method is the generation of a Meta-Model. 

The Stacking Generalization method is commonly composed of 2 training stages, “level 0” and “level 1”. 

It is important to mention that it can be added as many levels as necessary. However, in practice it is common to use only 2 levels. 

The aim of the first stage (level 0) is to generate the training data for the meta-model, this is carried out by implementing k-fold cross validation for each “weak learner” defined in the first stage. 

The predictions of each one of these“weak learners” are “stacked” in order to build such such “new training set” (the meta-model). 

The aim of the second stage (level 1) is to train the meta-model, such training is carried out through an already determined “final learner”.


**Blending:**

Blending is a technique derived from Stacking Generalization. 

The only difference is that in Blending, the k-fold cross validation technique is not used to generate the training data of the meta-model. 

Blending implements “one-holdout set”, that is, a small portion of the training data (validation) to make predictions which will be “stacked” to form the training data of the meta-model. 

Also, predictions are made from the test data to form the meta-model test data.


**Voting:**

The Voting Classifier is a homogeneous and heterogeneous type of Ensemble Learning, that is, the base classifiers can be of the same or different type. 

This type of ensemble also works as an extension of bagging (e.g. Random Forest).

The architecture of a Voting Classifier is made up of a number “n” of ML models, whose predictions are valued in two different ways: 

    Hard:
        In hard mode, the winning prediction is the one with “the most votes”. 
        
    Soft:
        Soft mode considers the probabilities thrown by each ML model, 
        these probabilities will be weighted and averaged, 
        consequently the winning class will be the one with the highest weighted and averaged probability.

