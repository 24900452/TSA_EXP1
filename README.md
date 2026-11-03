# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 23.10.2026
###  Name: Jothi Ganesh P
###  Reg no:212224240065

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:


from matplotlib import pyplot as plt
import pandas as pd

df = pd.read_csv("/content/nifty_it_index.csv")

df.head()

df['Date'] = pd.to_datetime(df['Date'])

df.dtypes

df.set_index('Date', inplace=True)

df_resampled = df['Close'].resample('D').interpolate()

df_resampled.plot(kind='line', label='Closing Price', color='black')

plt.title('Time Series Plot of Nifty IT Index Closing Price')
plt.xlabel('Date')
plt.ylabel('Closing Price')
plt.legend()
plt.grid(True)
plt.show()



# OUTPUT:
<img width="589" height="471" alt="download" src="https://github.com/user-attachments/assets/8f01484d-ce52-4167-b072-a4beb5e16daa" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.
