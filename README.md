 # Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1: Start the Program.

### Step 2: Import required libraries:

numpy for array handling.

sys to exit the program in case of divide-by-zero.

### Step 3: Input the Size and Augmented Matrix
Read the number of unknowns n.

Create an augmented matrix a of size n × (n+1) and a solution vector X of size n.

Take user input to fill the augmented matrix a.

### Step 4:  Forward Elimination 

For each pivot row i, check for divide-by-zero.

For all rows below i, compute the ratio a[j][i]/a[i][i] and eliminate the coefficient below the pivot.

### Step 5: Solve the last variable directly.

### Step 6: Solve remaining variables using previously computed values.

### Step 7: Print the values of all unknowns.
## Program:
```
import numpy as np
import sys
#Reading number of unknowns
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
#applying gauss elimination
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
#back substitution
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i] - a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
#displaying solution
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![Screenshot 2025-05-13 173208](https://github.com/user-attachments/assets/ffc22119-02d3-405b-91be-3b2b450997b7)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

