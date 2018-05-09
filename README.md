# practicalmachinelearning
Coursera Data Science - Practical Machine Learning Course Assignment: Modelling and Prediction for Personal Exercise Device

Files submitted for evaluation include .rmd file, html document, and .pdf file if the others are less readable

## Background
"Using devices such as Jawbone Up, Nike FuelBand, and Fitbit it is now possible to collect a large amount of data about personal activity relatively inexpensively. These type of devices are part of the quantified self movement - a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior, or because they are tech geeks. One thing that people regularly do is quantify how much of a particular activity they do, but they rarely quantify **how well** they do it. In this project, the goal will be to use data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants. They were asked to perform barbell lifts correctly and incorrectly in 5 different ways." [^1]

"Six young healthy participants were asked to perform one set of 10 repetitions of the Unilateral Dumbbell Biceps Curl in five different fashions: exactly according to the specification (Class A), throwing the elbows to the front (Class B), lifting the dumbbell only halfway (Class C), lowering the dumbbell only halfway (Class D) and throwing the hips to the front (Class E). Class A is the correct execution, and the other classess correspond to common mistakes."[^2] 

## Data
The dataset was provided by Ugulino, Cardaror, et. al.[^3], and is available from this source.[^2]  The dataset contains 19622 observations in the training and 20 observations in the testing set.  Columns majorly populated with data include 13 features for each of four devices worn on the belt, arm, dumbbell, and forearm (52 total).  These features are measurements corresponding to roll, pitch, yaw, total acceleration, and triaxial device data from the gyros, accelerometers, and magnetometers. Other columns include information on subjectID, time/window, and the outcome. The outcome is 'classe'. 

## Summary

### How the Model Was Built and Reasons for Choices
Three methods were used to fit the outcome (classe) to a set of 52 predictors: random forest, boosting with trees, and linear discriminant analysis, using the train function of the caret package. Default parameters were chosen, which included a 5-fold resampling. Accuracy was assessed from the prediction of the models individually and collectively, and the most accurate model (rf) was chosen. Additionally, the data did not appear to be linear, and the random forest method is robust for non-linear data. 

Two potential sources of noise were evaluated in the initial examination of data.  These include subjects not performing the same number of tests, and differences in the time windows. As the model fit was very good, these potential noise sources did not require further evaluation. 

### Cross Validation and Expected Out of Sample Error
The training data was partitioned in a 60/40 split to allow for training and to predict testing results. In-sample variation was obtained from model fit data, and was cross-validated by using predicted values from the test portion of the training data. The expected out-of-sample error is defined as 1-accuracy of the prediction from the test portion of the data, and is less than 0.8%.

* Please see project file for code and additional information *

### References
[^1]: Coursera Data Science Course, Practical Machine Learning, accessed 5/2018.
[^2]: http://groupware.les.inf.puc-rio.br/har 
[^3]: UVelloso, E.; Bulling, A.; Gellersen, H.; Ugulino, W.; Fuks, H. Qualitative Activity Recognition of Weight Lifting Exercises. Proceedings of 4th International Conference in Cooperation with SIGCHI (Augmented Human '13) . Stuttgart, Germany: ACM SIGCHI, 2013. 
[^5]: Greski, L., https://github.com/lgreski/datasciencectacontent/blob/master/markdown/pml-randomForestPerformance.md, accessed 5/2018.


