# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```python
DEVELOPED BY: RAMA E.K. LEKSHMI
REGISTER NUMBER: 212222240082
```
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
Load the data
```python
file_path = '/mnt/data/AirPassengers.csv'
data = pd.read_csv(file_path, index_col='Month', parse_dates=True)
```
Regular Differencing (without log transformation)
```python
data_diff = data.diff().dropna()

plt.figure(figsize=(10, 6))
plt.plot(data_diff, label='Regular Differenced Data', color='blue')
plt.title('Regular Differenced Time Series')
plt.xlabel('Year')
plt.ylabel('Differenced Number of Passengers')
plt.legend()
plt.show()
```
Seasonal Adjustment (subtracting the rolling mean to remove seasonality)
```python
rolling_mean = data.rolling(window=12).mean()
seasonal_adjustment = data - rolling_mean

plt.figure(figsize=(10, 6))
plt.plot(seasonal_adjustment, label='Seasonally Adjusted Data', color='green')
plt.title('Seasonally Adjusted Time Series')
plt.xlabel('Year')
plt.ylabel('Seasonally Adjusted Number of Passengers')
plt.legend()
plt.show()
```
Log Transformation
```python
data_log = np.log(data)

plt.figure(figsize=(10, 6))
plt.plot(data_log, label='Log Transformed Data', color='red')
plt.title('Log Transformed Time Series')
plt.xlabel('Year')
plt.ylabel('Log(Number of Passengers)')
plt.legend()
plt.show()


```

### OUTPUT:


REGULAR DIFFERENCING:

![d285b550-62db-41a2-b77d-50e569b2760f](https://github.com/user-attachments/assets/18349fc0-7b20-4641-9e74-9519d3c6438b)


SEASONAL ADJUSTMENT:

![b909e320-f2f4-4368-bad6-2e6fd8c71148](https://github.com/user-attachments/assets/0d81a25a-5416-4772-901c-e5619e2213f3)


LOG TRANSFORMATION:

![dbb3a936-c74a-44af-b141-bcd2e7607503](https://github.com/user-attachments/assets/3b976b3d-e326-4f10-ae45-2f2fdea5c508)



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
