# Algorithm for QR Decomposition

## Aim:

To implement QR decomposition algorithm using the Gram-Schmidt method.

## Equipment’s required:

1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm:

1.Intialize the matrix Q and u

2.The vector u and e is given by

[image](https://github.com/DINESH18032004/QRdecomposition/assets/119477784/f7d794ac-b3f3-4e13-a1e5-c61439326e5e)


[image](https://github.com/DINESH18032004/QRdecomposition/assets/119477784/5197555e-75fd-4889-9158-be3d6ce6e2f3)


[image](https://github.com/DINESH18032004/QRdecomposition/assets/119477784/d3f08b42-ff42-4027-8dc9-5a5f09442b44)


3.Obtain the Q matrix![image](https://github.com/DINESH18032004/QRdecomposition/assets/119477784/6fc53632-db42-4f1d-9abc-03184c8a07d7)

4.eqn4!Construct the upper triangular matrix R eqn5![image](https://github.com/DINESH18032004/QRdecomposition/assets/119477784/ed8639be-ecbd-4263-a3f2-4dff843a8812)




## Program:

### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by:DINESH KUMAR R
RegisterNumber: 212222110010
'''
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape
    
    Q = np.empty((n, n))
    u = np.empty((n, n))
    
    u[:,0] = A[:,0]
    Q[:,0] = u[:,0] / np.linalg.norm(u[:,0])
     
    for i in range(1, n):
        
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i]) @ Q[:, j] * Q[:, j]
        
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
        
    R = np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![8 maths](https://github.com/DINESH18032004/QRdecomposition/assets/119477784/181b5e06-3b63-412a-a316-eed6db1c806a)

## Result

Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
