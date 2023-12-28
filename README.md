# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

![image](https://github.com/Ajayreddy-2006/QRdecomposition/assets/145742508/af5c56e4-e873-45cf-8fe5-031eed6c99ac)


3.	Obtain the Q matrix   
![image](https://github.com/Ajayreddy-2006/QRdecomposition/assets/145742508/9981cb2f-ba61-4a76-b555-c05619714194)

4.	Construct the upper triangular matrix R



![image](https://github.com/Ajayreddy-2006/QRdecomposition/assets/145742508/44c87186-19a4-4cb4-a4c2-1c6a6457ccc1)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: your name:T.Ajay
RegisterNumber: 212223230007
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
            for j in range (i,m):
                R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)






```

## Output

![Screenshot 2023-12-27 183308](https://github.com/Ajayreddy-2006/QRdecomposition/assets/145742508/0cf9193d-3358-4d8a-a416-eca6e038330a)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
