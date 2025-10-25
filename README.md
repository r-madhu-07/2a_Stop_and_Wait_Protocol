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

Client.py
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

while True:
    i = input("Enter a data: ")
    c.send(i.encode())

    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

Server .py

```
import socket
s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recieved".encode())
```
## OUTPUT
Client.py

<img width="668" height="162" alt="image" src="https://github.com/user-attachments/assets/a159975d-ea17-4467-a9f0-1de88ad85ab1" />

Server.py

<img width="667" height="92" alt="image" src="https://github.com/user-attachments/assets/271fa5f8-81d3-4bcf-b659-f46be5d0b48b" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
