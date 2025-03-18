# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 11-03-2025
```
Name : Payyavula Jeshwanth Kumar
Register number : 212223240114
```

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:

### Import the necessary Packages
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
### Load the dataset
```
df=pd.read_csv('unq.csv')
```
### PLot the data without Conversion

```
x=df1['Date']
y=df1['High']

plt.plot(x,y)
plt.grid(True)
plt.title('Date vs High')
plt.xlabel('Date')
plt.ylabel('High')
plt.show()
```
### REGULAR DIFFERENCING
```
data3 = df
data3['diff'] = data3['High'].diff()
x = data3['Date']
y = data3['diff']
plt.xlabel('Date')
plt.ylabel('High')
plt.plot(x, y)
```

### SEASONAL ADJUSTMENT
```
data1 = df1
data1.loc[:, 'SeasonalAdjustment'] = data3['diff'].rolling(window=12).mean()
data1['SeasonalAdjustment'] = data1['SeasonalAdjustment'].dropna()
x = data1['Date']
y = data1["SeasonalAdjustment"]
plt.xlabel('Date')
plt.ylabel('SeasonalAdjustment')
plt.plot(x, y)
plt.show()
```
### LOG TRANSFORMATION
```
data2=df
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Date']
y=data2['log']
plt.xlabel('Date')
plt.ylabel('High')
plt.plot(x,y)
```

### OUTPUT:

### WITHOUT CONVERSION:

![image](https://github.com/user-attachments/assets/07030744-c1a3-4838-9742-cb122eb09e5e)


### REGULAR DIFFERENCING:

![image](https://github.com/user-attachments/assets/8027ba53-cb92-45e0-8846-fc7efad4288b)


### SEASONAL ADJUSTMENT:

![image](https://github.com/user-attachments/assets/891e6c18-6be5-4450-81a7-b8da093a9ee7)


### LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/bf9b3737-e9ca-4674-8a0c-c289f848a489)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
