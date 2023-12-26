# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
![ex4](https://github.com/Narendran-sec/QRdecomposition/assets/147473131/ed912cbf-efb4-4c6a-a4da-b9cb3abcabae)

![ex6](https://github.com/Narendran-sec/QRdecomposition/assets/147473131/28d11c04-c80f-4d99-a5c0-9dd2c46ee903)

3.Obtain the Q matrix 
![ex3](https://github.com/Narendran-sec/QRdecomposition/assets/147473131/bc1149ac-882c-4589-af19-8bcdc41fd7c4)
  ![ex2](https://github.com/Narendran-sec/QRdecomposition/assets/147473131/1cb6f822-94a2-4108-8439-4426b2c88e5d)

   

4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)




## Program:
### Gram-Schmidt Method
```



''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Narendran.k
RegisterNumber: 23013500
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range (1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i] -=(A[:,i] @ Q[:,j] * Q[:,j])
        Q[:,i]=u[:,i] / np.linalg.norm (u[:,i])
    R = np.zeros((n,m))
    for i in range (n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)




```

## Output

![qr output](https://github.com/Narendran-sec/QRdecomposition/assets/147473131/4a823a2f-ee3b-4817-8ce0-f7704a44c036)




## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
