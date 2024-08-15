# Implementation of Univariate Linear Regression
## AIM:
To implement univariate Linear Regression to fit a straight line using least squares.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the independent variable X and dependent variable Y.
2. Calculate the mean of the X -values and the mean of the Y -values.
3. Find the slope m of the line of best fit using the formula. 
<img width="231" alt="image" src="https://user-images.githubusercontent.com/93026020/192078527-b3b5ee3e-992f-46c4-865b-3b7ce4ac54ad.png">
4. Compute the y -intercept of the line by using the formula:
<img width="148" alt="image" src="https://user-images.githubusercontent.com/93026020/192078545-79d70b90-7e9d-4b85-9f8b-9d7548a4c5a4.png">
5. Use the slope m and the y -intercept to form the equation of the line.
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.

## Program:
```Py
/*
Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by: YUVAN SUNDAR S
RegisterNumber: 212223040250 
*/
import numpy as np
import matplotlib.pyplot as plt

X = list(map(float, input("Enter the independent variable X values separated by space: ").split()))
Y = list(map(float, input("Enter the dependent variable Y values separated by space: ").split()))

#converts list to array
X = np.array(X)
Y = np.array(Y)

mean_X = np.mean(X)
mean_Y = np.mean(Y)

numerator = np.sum((X - mean_X) * (Y - mean_Y))
denominator = np.sum((X - mean_X) ** 2)
m = numerator / denominator

#finding b
b = mean_Y - m * mean_X

# Equation of the line: Y = mX + b
Y_pred = m * X + b

# Plot the data points
plt.scatter(X, Y, color='blue', label='Data Points')

# Plot the regression line
plt.plot(X, Y_pred, color='red', label='Regression Line')

plt.xlabel('X')
plt.ylabel('Y')
plt.legend()
plt.show()
```

## Output:
![image](https://github.com/user-attachments/assets/dcde59d2-06b2-499b-8a80-efc34cc0731e)



## Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
