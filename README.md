# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
import os

os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np

def QR_Decomposition(A):

    A=A.astype(float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j].copy()
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]

    print("The Q Matrix is")
    print("",Q)
    print("The R Matrix is")
    print("",R)
a=np.array(eval(input()))

QR_Decomposition(a)

## Output:
<img width="1072" height="511" alt="image" src="https://github.com/user-attachments/assets/5766ffec-17cb-4bfd-bbfc-3c3c475d1dd5" />
<img width="1227" height="566" alt="image" src="https://github.com/user-attachments/assets/be6cdca5-71bc-41c7-af4f-c21a5e1dad5d" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
