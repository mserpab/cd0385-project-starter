# Report: Predict Bike Sharing Demand with AutoGluon Solution
MARICRUZ SERPA

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I didn't need to make any changes to my predictions, as all of the values were already positive. But I did validate that this condition was holding for the predicted data. Also, I had to adjust this predictions to the format of the submissions template in order to upload them to Kaggle.

### What was the top ranked model that performed?
It was the Weighted Ensemble L3. 

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
It helped understand the data better, and see how the different variables were behaving in order to create new features that made sense. I added additional date features, using the date field that we had in the data, but parsing it to the correct format in order to split it into hour, day, month, year columns.

### How much better did your model preform after adding additional features and why do you think that is?
The model really improved, the Kaggle score went from 1.79657 to 0.71865. I think this happened because the bike demand follows a chronological trend, that initially we weren't able to capture as date info was compressed into one single value, difficult for the model to understand and train on. But opening it up into more fields allowed the model to read this behavior. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The Kaggle score was reduced from 0.71865 to 0.46170.  

### If you were given more time with this dataset, where do you think you would spend more time?
I would read more documentation on Auto Gluon to understand the working of the specific models it runs, and see if I could try any additional hyperparameters to keep improving. Also, maybe some additional feature engineering to improve the data. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|time|num_bag_folds|num_stack_levels|score|
|--|--|--|--|--|
|initial|600|8|3|1.79657|
|add_features|600|8|3|0.71865|
|hpo|600|8|3|0.46170|
|add_features_hpo|700|9|4|0.67703|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
Even though i got the best Kaggle score from the last model (HPO), the best training evaluation metric was obtained with the second model (new features). Seeing that this one didn't perform as well on test data, I would believe the new feature model was overfitting on training data.  
