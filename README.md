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
## client
```
import socket

s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

## server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```


## OUTPUT
## client
![322496676-285f80ef-2e8d-41a6-b734-0fb4f35e819e](https://github.com/user-attachments/assets/9de554be-22c9-4a76-9b5f-db314a9c2ea6)

## server

![322496812-ca3a1f95-8af3-4ac3-9768-0609e6ece1a4](https://github.com/user-attachments/assets/3592b0f1-80b7-48a4-966a-2b7e682f85a3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
