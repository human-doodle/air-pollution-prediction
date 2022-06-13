# Air Pollution Prediction : Project Overview

* Forcasted the pollution at the next hour given the weather conditions and pollution for prior hours.
* Worked on the dataset from UCI Machine Learning Repository that reports on the weather and level of pollution each year at the US Embassy in Beijing
* Prepared data and transformed it into a supervised learning problem.
* Fitted an LSTM on the multivariate- input data. 


## Data Cleaning & Preparation

Made following changes to make it usable for the model:

*	Consolidated the date-time information into a single date-time to use as an index in Pandas.
*	"No" column dropped, rows with na values dropped and columns renamed. 
*	Normalised the input variables.
*	Transformed the existing dataset into a supervised learning problem to predict the pollution at current hour given pollution measurement and weather conditions at the prior timestep.
*	The weather variables for the hour to be predicted are removed
*	One-hot encoded the wind-dir 


## EDA
Looked at the distributions of the data. 
![alt text](https://github.com/human-doodle/air-pollution-prediction/blob/main/img/Line-Plots-of-Air-Pollution-Time-Series.png![image](https://user-images.githubusercontent.com/46643099/173430746-06b01b3d-6b8b-4da9-963f-c00f40b4c101.png)
 "Line Plots of air pollution time series")

## Model Building 

* The data was split into train and test set with 4 years of data in training set and 1 year of data in test set.   
* Then the sets were split into input(X) and output(y) variables
* Reshaped the inputs(X) into 3D format as expected by LSTMs - [samples, timestamps, features] 
* Defined LSTM with 50 neurons in the first hidden layer and 1 neuron in the output layer for prediction.
* Used Mean Absolute Error(MAE) loss function and the Adam version of stocastic gradient descent.
* Fit the model for 50 training epochs with a batch size of 72.
* Plotted graph for training and test losses

* ![alt text](https://github.com/human-doodle/air-pollution-prediction/blob/main/img/trainvstest.png

![image](https://user-images.githubusercontent.com/46643099/173431040-93cc02a2-176f-4c8f-a53f-81d21ce35c0b.png)
 "Train vs Test Loss")


## Model performance

* Model acheived Root Mean Squared Error(RMSE) of 25.004

## Code and Resources Used 
**Python Version:** 3.10.4  
**Packages:** keras with tensorflow backend, SciPy, Scikit-learn, pandas, numPy, matplotlib
**Reference**: Machine Learning Mastery- Jason Brownlee
