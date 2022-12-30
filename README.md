# Water-quality-project
Water potability prediction <br>
Analysing a dataset on water quality <br>
This project starts with a dataset and its analysis is not defined in every detail, just like a real Data Science project. There are no precise instructions but simply a guideline that I consider to be fairly standard and general for each problem. <br>
Your task will be to follow each point and comment on it, showing me that you understand what you are doing. If some points prove impossible, explain the reason why. You will probably find some models or techniques that you have not really studied. Don't worry, experimentation, discovery and continuous updating are part of the game. <br>
 
EDA <br>
First of all, divide the dataset into a training part and a testing part. Start analysing the dataset. Pay attention to which dataset to use for each point (training, test or all?). Among other things, also consider:<br>
- Are outliers present (check feature by feature and plot feature values vs. classes)? If yes, what percentage? <br>
- The various features may have very different values. This is not good for almost any ML algorithm, so consider applying a Standardisation to the dataset, such as StandardScaler(). Be careful to exclude the label column! <br>
Then ask yourself the following questions: <br>
- Are there any features with missing values? What do you do? Comment on your analysis clearly. <br>
- Is the dataset balanced? If not, proceed to balance it. Use the stratified sampling method  and explain why it is often better than random sampling. <br> 
- How correlated are the variables? Are there linear relationships? Then calculate the correlation matrices, give an interpretation and explain whether or not it is useful to use linear models. <br>
- Are all variables necessary or can I select a subset and neglect the others? Perform a T-test (hypothesis testing) to see which features are significantly different in class 0 and class 1 and thus reject the null hypothesis, i.e. the one that says that the average of the features for the two classes is the same. These features are the ones that might (we need to check!) best distinguish one class from the other. <br>

Choose the proper metric <br>
Once we understand the type of task to be solved (in our case it is a binary classification), an important step that determines all future evaluations is the choice of metrics with which we are going to measure performance. <br>
The first is accuracy, but it is not the only one that is relevant. Try to understand what the others are and define them one by one. From now on you will use accuracy to evaluate the goodness of models. <br>

Model definition, training, hyperparameter tuning <br>
Think now about how to approach and set up the problem of predicting health status: Normal, Suspect, Pathological. Choose the following models: Logistic Regression, RandomForest Classifier and K-nearest neighbours (how do you choose the number k?). For each model you choose, read the documentation on sklearn. <br>
Now let's try two different ways. The road we call 1) consists of using all available features, while the road we call 2) consists of selecting the features (3 or 4) that proved to be most relevant according to the Mutual Information or ANOVA f-test above. <br>

Therefore perform the following procedure for both paths, first with 1) then with 2). <br>
1- Perform a spot check on the chosen models and select the two best models using StratifiedKFold k-fold cross validation with one of the metrics discussed above as evaluation method (use the whole training set as dataset. The cross validation procedure will then divide the various k-folds into training and validation). The spot check is not intended to be a complete training but just a quick procedure to see if there are any types of models that stand out more than others. <br>
2- Then carry out a tuning of the hyper-parameters on these two best models, e.g. using a grid search and always cross validation as an evaluation method (there is a GridSearchCV method on sklearn). You should now be in a position to know the best hyperparameters for both selected models. <br>
Now evaluate the two models on the hitherto unused test set. You will see which one performs better by comparing the values of the chosen metrics. <br>
Final Evaluation<br>
Now compare routes 1) and 2) and obtain the best model. Make a final discussion about the problem and the solution found. <br>
Notes: I suggest to open the notebook with nbviewer at this link: 
