# Senior_Comps_Stock_LSTM_AR
R - .Rhistory 

Python - AR_models_and_performance_check.ipynb, Data Preprocessing and auto-correlation tests.ipynb, LSTM.ipynb, Model Performance Check.ipynb

Excel - Stats.xlsx contains the statistical results. returns_1 ~ returns_6 are stock returns in different time periods. results 1 ~ 6 are the results of the original LSTM model. n_result 1 ~ 6 are the results of the second LSTM model with LSTM layers. 

model_performance.txt has the history of the first LSTM model's accuracies and binary cross entropies for each time period


1. Gather data
S&P 500 indices can be acquired from Yahoo! Finance, but the one I used for the project has been uploaded.

2. Data Preprocessing
Simply execute through the Data Preprocessing and auto-correlation tests.ipynb. It will calculate the daily returns and log differences of closed adjusted prices. It will also divide the data sets into 6 consecutive 15-year periods and save them as separate csv files.

3. Statistical Tests
The second half of Data Preprocessing and auto-correlation tests.ipynb will provide some basic measures, such as mean and standard deviations for each time period. It also provides the first 20 autocorrealtions for each time period. For Lo-Mackinly VR test, Automatic VR test, and Automatic Portmanteau test, which all test random walks hypotehsis, R can be used. .Rhistory contains my codes for these statistcal tests. 

4. LSTM
LSTM.ipynb contains everything that invovles with the implemntation of LSTM. Choose the return csv file that was acquired from step 2. The code is streamlined to execute and return results for different time periods. The uploaded code shows the LSTM structure for the second LSTM model employed in the paper. Thus, to re-produce this research, the second and third layers of LSTM will need to be commented out along with the return_sequences = True in the first LSTM layer. The actual predictions are converted as arrays and are saved under different result numbers. 

5. Model Performance Check
Model Performance Check.ipynb is used to check the performance of model. result csv file is read and the directional accruacy, + accruacy, - accuracy, % of + prediction are all calculated. Additoinally, the first block is capable of evaluating the trading strategy exctracted from the models.

6. AR and performance check
AR_models_and_performance_check.ipynb contains everything that invovles AR. Simliar with LSTM, the same block of code is ran multiple times with different input csv files. This code establishes the correlation coefficients for lag=1 or lag=1~20 from the trainig period and uses those coefficients to make predictions in testing period. The model performnace is also evaluted in the same block.
