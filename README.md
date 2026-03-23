# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```import matplotlib.pyplot as plt
import numpy as np

# Example data (replace with your own dataset or load from CSV)
data = [3, 16, 156, 47, 246, 176, 233, 140, 130, 101, 166, 201, 
        200, 116, 118, 252, 153, 232, 128, 27, 192, 168, 208, 
        187, 228, 86, 30, 151, 18, 254, 76, 112, 67]

# Convert to numpy array
data = np.array(data)

N = len(data)
lags = range(35)
autocorr_values = []

mean_data = np.mean(data)
variance_data = np.var(data)

# Compute autocorrelation for each lag
for lag in lags:
    if lag == 0:
        autocorr_values.append(1)  # Autocorrelation at lag 0 is always 1
    else:
        auto_cov = np.sum((data[:-lag] - mean_data) * (data[lag:] - mean_data)) / N
        autocorr_values.append(auto_cov / variance_data)  # Normalize by variance

# Plot autocorrelation
plt.figure(figsize=(10, 6))
plt.stem(lags, autocorr_values, use_line_collection=True)
plt.title('Autocorrelation of Data')
plt.xlabel('Lag')
plt.ylabel('Autocorrelation')
plt.grid(True)
plt.show()
```

### OUTPUT:
<img width="1362" height="693" alt="image" src="https://github.com/user-attachments/assets/7f0899b4-2af6-468f-822a-aa8d4e6f71a0" />

### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
