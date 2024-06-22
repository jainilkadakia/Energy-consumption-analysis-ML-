# Energy-consumption-analysis-Machine Learning 
This project aims to predict electricity consumption in Finland using time series 
data and a Long Short-Term Memory (LSTM) neural network. The dataset 
events (1).csv was loaded and cleaned by dropping irrelevant columns and 
renaming others for clarity. Key temporal features such as month, year, date, 
time, and day were extracted from the datetime column.
Exploratory data analysis included:
Line Plot: Visualizing electricity consumption trends from 2016 to 2021.
Distribution Plot: Showing the distribution of electricity consumption.
Box Plots: Comparing electricity consumption across different months and 
years.

The dataset was then indexed by datetime and resampled daily. Afterward, the 
data was normalized using MinMaxScaler. The dataset was split into training 
(60%), testing, and validation subsets.
A function create_dataset was implemented to prepare the data for the LSTM 
model by creating sequences of past observations to predict future values. A 
time step of 100 was used for sequence length.

The LSTM model was constructed with three LSTM layers, each with 50 units, 
and a dropout rate of 20% to prevent overfitting. The model was compiled using 
the Adam optimizer and mean squared error loss function.The model was 
trained for 60 epochs with a batch size of 20, and its performance was 
monitored using both training and validation losses. The loss curves were 
plotted to visualize the training process.
Model predictions on the training set were made and then inverse transformed 
to their original scale. The predictions were compared against actual values, and 
results were plotted to show the alignment between actual consumption and 
predicted values
