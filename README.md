# Disney World Wait Times
## Predictive Multivariate Time Series Model

### Summary
Can wait times for a Disney World attraction be predicted?

A recurrent neural network is used to predict wait times for the Walt Disney World attraction, Pirates of the Caribbean. Long short-term memory (LSTM) is used from the Keras library to create a predictive model. This project demonstrates the full data science process from data wrangling, exploratory data analysis, model building and making predictions.

The wait time data used was collected from 2016-2019. Additional variables such as weather, park hours, holidays, parades, and percentage of schools in session were used as input variables. It was trained on two years worth of data, tested on 1 year of data, and finally validated on 1 additional year of data. Predictions are compared to the actual wait times to further gain an understanding of how well the model performed.

### Data
Touring Plans: Disney Wait Time Data for Machine Learning and Data Science Projects - https://touringplans.com/walt-disney-world/crowd-calendar#DataSets

### Tools
* Keras
* Pandas
* Scikit-learn
* Matplotlib

### Modeling methods
* Neural network
* LSTM

The time series data was reformatted for a supervised learning algorithm using one timestep in the past to predict one future timestep.

The final model used 1 LSTM layer with constraint of 50 and 1 dense layer. The training set was fitted on 100 epochs with a batch size of 72.

The training set started to smooth out after about 40 epochs. The test set had fluctuations in residuals always just above the training set without overfitting or underfitting the data, but never converging.

![Train Validation Loss](/graphs/wait_train_val_loss.jpg)

### Results
On the validation set, the final model produced an RMSE of 7.174, which equates to 7.174 minute variance from the actual wait time.

10% of the predicted values are plotted against the actual values. The lines fall very close to each other, following the same trends through each timestep in the data.

![Predictions](/graphs/wait_predicted_vs_actual.jpg)

### Navigation

data - Folder containing data used in this project
graphs - graph outputs from the notebooks
results - test and validation predictions
Pirates_DataPrep_EDA.ipynb - Data preparation and exploratory data analysis
Pirates_LSTM_Model1Step.ipynb - Different models tested using 1 past timestep
Pirates_LSTM_Model4Step.ipynb - Different models tested using 4 past timesteps
