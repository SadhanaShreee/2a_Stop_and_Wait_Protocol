# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
```
 CLIENT:

import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
 if ack:
    print(ack)
 c.close()

 
SERVER:
     
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
print(s.getsockname()) 
print(s.recv(1024).decode()) 
s.send("acknowledgement recived from the server".encode()) 


```
## OUTPUT

![Screenshot 2024-05-27 084007](https://github.com/SadhanaShreee/2a_Stop_and_Wait_Protocol/assets/144517664/ecdd78c0-0b3b-47fc-9828-16e1e80da2ad)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
