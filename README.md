# PA2-Numerical-Python-NumPy-
This repository serves as a submission. This program was made and written in partial fulfillment of the requirements for Advanced Computer Programming and Algorithms (ECE2112).

## Description
This program solves two different problems given using incorporated codes and functions in the Numerical Python (NumPy) library.

## Instructions
Write a Python script/code in the Jupyter Notebook to do the given problems.

### Importing NumPy Library
```
import numpy as np
```
Before writing the code, the NumPy Library was imported. This grants access to the ndarray object and its associated operations and functions.

### Problem #1: Normalization Problem
In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized ndarray as X_normalized.npy

**Solution**
```
x = np.random.random((5,5)) # Random Array

# Computation
mean = x.mean()
std = x.std()
z = (x - mean)/std # Normalization formula

# Save and Load array
np.save('X_normalized.npy', z) 
np.load('X_normalized.npy')
```
<br>
Firstly, the array was initialized using the variable "x", which was assigned the 5 x 5 array with randomized values. Next, the "mean" variable stored the mean of the array (using the ".mean" call) and the "std" variable stored the standard deviation of the array (using the ".std" call). The "z" variable is used to store the normalization formula: <br><br>

```
Z = (X - x̄) / σ. 
```
wherein:
* Z is the "z" variable, representing the normalized value.
* X is the "x" variable, representing the random number from the array.
* x̄ is the "mean" variable.
* σ is the "std" variable.
<br>
The array was then saved as "X_normalized.npy" and then loaded to show the result.
<br><br>

**Results**
```
array([[-1.3274631 ,  1.44955219, -0.65093186, -1.24015547, -1.07381586],
       [ 1.18786251,  1.29717136,  1.32980706,  0.21001044,  1.02926689],
       [ 0.72733454,  0.33821173, -1.09456486,  1.03222271, -0.12657363],
       [-1.04856448, -0.20022859, -0.30698896,  0.96201737, -1.28175046],
       [ 0.12410343, -1.00661304, -0.92700785, -0.97911862,  1.57621657]])
```
<br>
The copy of this result is found here: https://github.com/JaqlynBernardo/PA2-Numerical-Python-NumPy-/blob/main/X_normalized.npy

### Problem #2: Divisible by 3 Problem
Create a 10 x 10 ndarray which are the squares of the first 100 positive integers. From this ndarray, determine all the elements that are divisible by 3. Save the result as div_by_3.npy

**Solution**
```
# Array with the squares of the first 100 natural numbers 
num_list = list(range(1,101)) # list of first 100 natural numbers
num_array = np.square(num_list)
A = num_array.reshape(10,10)

# Numbers divisible by 3
div_by_3 = []
for x in A.flatten():
    if x%3 == 0:
        div_by_3.append(int(x))

# Save and Load array
np.save('div_by_3.npy', div_by_3) 
np.load('div_by_3.npy')
```

First, in the "num_list" varaible, using the range() function to generate the first 100 natural numbers inside a list data structure. Then, variable, "num_array", takes the square of each element inside the list, and stores it into its own array. The numbers inside the "num_array" is then taken and reshaped into a 10 x 10 array, inside of varaible "A".
<br><br>
To get all the numbers divisible by 3, first, an empty list, "div_by_3", was created to be the placeholder. Next, the for loop takes each element in the flattened array "A" (so that each element can be accounted for instead of each row). Inside the loop is an if statement that checks if each element has a remainder equal to zero when divided by three. If the if statement is satisfied, the number will be appeneded into the empty list. Lastly, the array "div_by_3" array is saved as "div_by_3.npy" and then loaded to show the result.


**Results**
```
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```
<br>
The copy of this result is found here: https://github.com/JaqlynBernardo/PA2-Numerical-Python-NumPy-/blob/main/div_by_3.npy


## Author
Bernardo, Jaqlyn Trazy B.
* Section: 2ECE-C
* Student No.: 2024198347
