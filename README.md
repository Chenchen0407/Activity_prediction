# Activity_prediction
Activity prediction models are established to predict the activity information. The repository includes models of the recreation of the TimeGeo model and the updated Activity Scheduler model.

## Sequential Activity Scheduler Model

This repository contains the Sequential Activity Scheduler Model, a model for predicting sequential activities. It uses a decision tree algorithm and is trained with data from the 2010-2012 California Household Survey. 

### Model Components

The model has two components: The Activity Type Model (ATM) and the Activity Duration Model (ADM). 

#### Activity Type Model (ATM)
The ATM uses a decision tree model to predict the type of the next activity based on individual attributes and the current activity's end time. It involves two key mechanisms: the 'back and stay-home mechanisms which categorize individuals into employed, student, or other, and a splitting mechanism which divides the samples based on the activity's end time. 
![image](https://github.com/Chenchen0407/Activity_prediction/assets/117785853/3dd20890-cdd3-48b2-8e20-596d39fc95a0)
The tree's nodes are split based on maximizing information gain and continue to split until the information gain is lower than a set threshold (in this case, 0.02). 

#### Activity Duration Model (ADM)
The ADM uses the activity type determined by the ATM and other context features (such as end time of current activity, gender, driver’s license state, and education) to determine the duration of the next activity. Unlike the ATM, which outputs a discrete probability distribution, the ADM models a continuous one. 

### Sequential Activity Prediction
The model generates sequential activities, starting with the first activities and personal attributes in the dataset, and continues to generate activities until the activity type is predicted as 'none'. 

