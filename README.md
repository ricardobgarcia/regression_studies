# Regression Studies

## Abstract
This is a Data Science study project motivated by my interest in developing a visual intuition about regressions using Decision Trees and Random Forests. 
The first time I've studied these models, the lectures and practices were focused on classifications problems. In another course (Kaggle's Introduction to Machine Learning), these models were presented in the context of regression problems. So, I've developed this study project for consolidating my knowledge.
I've chosen a small dataset that allowed the three-dimensional visualization of the variables and the solution space of the models. The results are very illustrative of their nonlinear behavior and help better  understand their capacity of solving complex multidimensional problems.

## Introduction
<b>Decision Trees</b> have this name because of their tree-like structure: from a single initial root node (which has all the sample data "inside" it), the algorithm iteratively searches the features to find the optimal split point that separates the data subset that summarizes part of the target with the minimum error. Then, for this subset, the algorithm repeats the search procedure to find the optimal split point, and so on until a stop criterion is met (e.g., a specified depth level is achieved). Once this terminal node is achieved, the algorithm next steps involve solving the split problem for the remaining subsets. The result is a set of terminal nodes generating the target predictions with errors minimized.

<b>Random Forests</b> have this name because they are a collection of random decision trees, that is, each single tree is trained with a random sampling of features and observations, in a way that each one develops a solution to the observed part of the data with the resources (features) available. The forest then combines the output of several decision trees to reach a solution.


## The problem
For investigating the regressions in the three-dimensional space, I've chosen a small dataset with a nonlinear shape. It consists of 100 observations of students' marks that should be predicted by the number of courses attended and study time. The boxplot summarizes the data distibution and in the three-dimensional scatterplot we can observe Marks as a function of number of courses and study time.




<p align="center">
  <img alt="Light" src="/figures/boxplot.png" width="45%"
  <figcaption align="center"><br><b>Figure 1.</b> Boxplot of the features and the target.</figcaption>
</p>
<br>
<p align="center">
  <img alt="Dark" src="/figures/scatterplot3.png" width="40%"
  <figcaption align="center"><br><b>Figure 2.</b> Scatterplot showing the nonlinear distribution.</figcaption>
</p>



## Model development 
- The dataset was splitted into a training set (70%) and a validation set (30%) for assessing the generalization to new data.
- The absolute distance from each prediction to the actual value were computed and averaged. This is known as the Mean Absolute Error (MAE), which indicates how much the predictions deviated in average from the actual values.
- An artificial data set of 600 number_courses/time_study pairs was created for plotting the range of model's predictions.
- Four models were developed: a baseline Mean Model to serve as an initial reference, a Linear Regression Model to get the linear fit, a Decision Tree, and a Random Forest Model; these latter twos for visualizing their nonlinear behavior.

## Models
### Mean Model
This model simply returns the mean of the target variable (Marks) of the training set for any test set provided. The Figure below shows the Mean Model behavior depicted in blue color, with the training set data in green and the validation data in orange. The MAE for the training and validation sets were 11.35 and 12.85, respectively.

<p align="center">
  <img alt="Light" src="/figures/mean_model.png" width="40%"
  <figcaption align="center"><br><b>Figure 3.</b> The baseline Mean Model.</figcaption>
</p>





### Linear Regression Model
The animations below show the model's predictions in comparison with the actual values, as well as the model behavior. The MAE for the training and validation sets were 3.19 and 2.73, respectively.

<p align="center">
  <img src="/figures/modelv_lr.gif" width="40%"/> <img src="/figures/model_lr.gif" width="40%"/> <br>
  <b>Figure 4.</b> In the left panel, we see the comparison between the actual values (in orange) and the predicted values (in red). 
                  In the right panel, we see in blue the range of model's predictions.
</p>

### Decision Tree Model
The animations below show the model's predictions in comparison with the actual values, as well as the model behavior. The MAE for the training and validation sets were 1.99 and 2.36, respectively. 

<p align="center">
  <img src="/figures/modelv_dt.gif" width="40%"/> <img src="/figures/model_dt.gif" width="40%"/> <br>
  <b>Figure 5.</b> In the left panel, we see the comparison between the actual values (in orange) and the predicted values (in red). 
                  In the right panel, we see in blue the range of model's predictions.
</p>

### Random Forest Model
The animations below show the model's predictions in comparison with the actual values, as well as the model behavior. The MAE for the training and validation sets were 0.58 and 0.99, respectively.

<p align="center">
  <img src="/figures/modelv_RF.gif" width="40%"/> <img src="/figures/model_RF.gif" width="40%"/> <br>
  <b>Figure 6.</b> In the left panel, we see the comparison between the actual values (in orange) and the predicted values (in red). 
                  In the right panel, we see in blue the range of model's predictions.
</p>
