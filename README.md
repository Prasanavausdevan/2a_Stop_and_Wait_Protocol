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
## PROGRAM
client.py
```

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
![Screenshot (39)](https://github.com/Prasanavausdevan/2a_Stop_and_Wait_Protocol/assets/144870579/82f4e433-5a56-4cbf-880b-5c9d37961823)
![Screenshot (38)](https://github.com/Prasanavausdevan/2a_Stop_and_Wait_Protocol/assets/144870579/089d83b3-3b89-4e79-8cf7-c46cbc80320f)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
