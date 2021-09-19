# [Weekly Data Problem 10 ITSL](https://github.com/ModelBehavior/tecator/blob/main/teactor.Rmd)
### Data Description
This data contains 1,089 weekly returns for 21 years, from the begininning of 1990 to the end of 2010. The predictors are lag 1-5, and volume. The reponse variable is direction (Up or Down).

### Goals of Analysis
The goal of this analysis is to fit a logistic regression, LDA, QDA, and KNN models to the data using all predictors and see which model gives the best results.

### Methodology
The data was split into a training and testing set. Repeated 10-fold cross-validation was performed with the training data to tune KNN and to get the average performance of models on the training data. The metrics recorded were accuracy, kappa, sensitivity, specificity, PPV, and NPV. We can see that logistic regression and linear discriminate analysis did equally well on this dataset, with accuracy above 54%. The kappa statistics are close to zero, meaning there is little to no agreement between the observed and predicted classes. The two best models, based on accuracy, have low sensitivity. The sensitivity is the rate that the event of interest is predicted correctly for all samples having the event. The event, in this case, is the response level down. Meaning the models predict down as up at a high rate. Conversely, the models have high specificity. Meaning the models predict up as up with a high rate. In other words, the true positive rate is high, and the false positive rate is low. We are also more likely to trust the model when it predicts up as opposed to predicting down.

![](https://github.com/ModelBehavior/Weekly/blob/main/weekly_image)

Update:
Added a baysian anova test to see if models are statistically different from one another based on accurcay.

### Results 
Using logistic regression as the final model. The accuracy on the test set was 0.5018315, and the area under the roc curve was 0.5206213. This doesn't seem like much, but the stock market is very hard to predict.
