# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
(i) To find the L and U matrix
   1. Take the input as a square matrix A.
   2. Convert the input into a Numpy array for mathematical operations.
   3. Use the lu function from the scipy .linalg library to compute the LU decomposition of matrix A,which returns permutation matrix p, lower triangular matrix L, and upper triangular matrix U.
   4. Print the variable 'L' and 'U'.
<br>
(ii) To find the LU Decomposition of a matrix
   1. Define the package as scipy.linalg import lu.
   2. Take two inputs from the user: A: A square matrix (coefficient matrix) B: A vector (right-hand side of the linear equations).
   3. Convert the inputs into Numpy arrays for the numerical operations.
   4. Use the lu_factor function from scipy.linalg to compute the LU decomposition of a matrix A. This returns: lu: Combined LU decomposition. piv: Pivot indicates.
   5. Use lu_slove with the LU decomposition (lu,piv) and vector b to compute the solution vector x.
   6. Print the variable 'X'.
   
## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: R P Loshini
RegisterNumber: 25002119
'''
import numpy as np
n = int(input())
matrix = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j] = int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio = matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k] = matrix[j][k]-ratio*matrix[i][k]
#Back Subsitution
x[n-1] = matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i] = matrix[i][n]
    for j in range(i+1,n):
        x[i] = x[i]-matrix[i][j]*x[j]
    x[i] = x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]), end=" ")
```

## Output:
<img width="1149" height="501" alt="Screenshot 2025-11-29 201000" src="https://github.com/user-attachments/assets/7b949a24-9f25-49d2-9f1e-3794cf7a4429" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

