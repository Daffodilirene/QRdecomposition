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
```
Developed by: DAffodil Irene .S 
RegisterNumber: 212225100006
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"

import numpy as np

def QR_Decomposition(A):
    m, n = A.shape
    q = np.zeros((m, n))
    r = np.zeros((n, n))

    for j in range(n):
        v = A[:, j].copy()

        for i in range(j):
            r[i, j] = np.dot(q[:, i].T, A[:, j])
            v = v - r[i, j] * q[:, i]

        r[j, j] = np.linalg.norm(v)
        q[:, j] = v / r[j, j]

    return q, r

a = np.array(eval(input()))

q, r = QR_Decomposition(a)

print("The Q Matrix is\n", q.round(8))
print("The R Matrix is\n", r.round(8))<img width="957" height="400" alt="Screenshot 2026-05-31 161119" src="https://github.com/user-attachments/assets/1499601b-9c79-4ae1-8e82-136201964bd2" />

```

## Output

<img width="957" height="400" alt="Screenshot 2026-05-31 161119" src="https://github.com/user-attachments/assets/468ee5db-c656-48ab-9b4c-a24e6a8c4c07" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
