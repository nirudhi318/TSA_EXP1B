# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 09/02/2026

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
df = pd.read_csv('/content/data.csv')
df = df[['price']].dropna()
plt.figure()
plt.plot(df['price'])
plt.title('Original Price Data')
plt.show()
df['log_price'] = np.log(df['price'])

plt.figure()
plt.plot(df['log_price'])
plt.title('Log Transformed Price')
plt.show()
df['diff_price'] = df['price'].diff().dropna()

plt.figure()
plt.plot(df['diff_price'])
plt.title('Regular Differenced Price')
plt.show()
plt.figure()
plt.plot(df['seasonally_adjusted'])
plt.title('Seasonally Adjusted Price')
plt.show()
df['diff_log_price'] = df['log_price'].diff()

plt.figure()
plt.plot(df['diff_log_price'])
plt.title('Log Transformed + regular differencing')
plt.show()
df['diff_log_price'] = df['log_price'].diff()

plt.figure()
plt.plot(df['diff_log_price'])
plt.title('Log Transformed + regular differencing + seasonal differencing ')
plt.show(
plt.figure(figsize=(10,8))

# Explicitly calculate log_diff and log_diff_seasonal to ensure they exist
df['log_diff'] = df['log_price'].diff()
df['log_diff_seasonal'] = df['log_diff'].diff(periods=seasonal_period)

plt.subplot(4,1,1)
plt.plot(df['price'])
plt.title('Original Price')

plt.subplot(4,1,2)
plt.plot(df['log_price'])
plt.title('Log Transformed')

plt.subplot(4,1,3)
plt.plot(df['log_diff'])
plt.title('Log + Regular Differencing')

plt.subplot(4,1,4)
plt.plot(df['log_diff_seasonal'])
plt.title('Log + Regular + Seasonal Differencing')

plt.tight_layout()
plt.show()
```
### OUTPUT:

ORIGINAL PRICE DATA:

<img width="547" height="435" alt="original price" src="https://github.com/user-attachments/assets/55e456c6-5938-46dd-ba35-49551375ae48" />

LOG TRANSFORMED PRICE:

<img width="543" height="435" alt="LOG TRANSFORMED PRICE" src="https://github.com/user-attachments/assets/1993c9bf-e289-4d83-b21f-c27a3623adcb" />

REGULAR DIFFERENCING:

<img width="546" height="435" alt="REGULAR DIFFERENCING" src="https://github.com/user-attachments/assets/4bcc295f-0aa4-4ceb-bad2-9f024e441f4e" />

SEASONAL ADJUSTMENT:

<img width="547" height="435" alt="SEASONAL ADJUSTMENT" src="https://github.com/user-attachments/assets/b6bd7139-524e-4f13-9eb6-12c2f1155ad4" />

LOG TRANSFORMATION:

<img width="546" height="435" alt="LOG TRANSFORMATION" src="https://github.com/user-attachments/assets/bc281bc8-cb8f-4fc7-9628-119dd612616b" />


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
