# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Importing Numpy Module and Sys module
2.Initialize the matrix with zeros and get inputs and store it
3.Solve the matrix using gaussian elimination method
4.Print the result

## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Sre Vishnu Priyar L N
RegisterNumber: 26009605
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
<img width="1493" height="908" alt="image" src="https://github.com/user-attachments/assets/43520648-b9fa-4e89-8a75-4bde013d3704" />
<img width="1480" height="885" alt="image" src="https://github.com/user-attachments/assets/e183d07b-5040-4272-9453-45041dea3d6e" />
<img width="1490" height="747" alt="image" src="https://github.com/user-attachments/assets/20efc098-885f-43ed-9550-8a19e23b65b4" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

