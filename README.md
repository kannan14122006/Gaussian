# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries numpy and sys.

2. Input the size of the matrix n and define augmented matrix a as a NumPy array of size (n, n+1). Initialize the solution array x as a NumPy array of size n.

3. Perform forward elimination to transform the augmented matrix into an upper triangular form:

.For each pivot row, ensure the pivot element is non-zero.
.Subtract multiples of the pivot row from the rows below to eliminate the elements below the pivot.


4. Perform backward substitution to compute the solution:

Start with the last variable and substitute back into the equations to find the remaining variables

5. Display the solution values of all variables using formatted output.

6.Verify the results for correctness.


## Program:

/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: kannan R
RegisterNumber: 212224240072
*/

```
import numpy as np
import sys
n = int(input())
a = np.zeros((n, n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n + 1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i +1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]- ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2, -1,-1):
    x[i] = a[i][n]
    for j in range(i+1, n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end=" ")
```
## Output:

![image](https://github.com/user-attachments/assets/ae3c5ac6-e587-444c-b77f-406eca0cfc14)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

