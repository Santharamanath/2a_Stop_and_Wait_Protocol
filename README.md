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
## Client:
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

## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## Client:
![360306782-56999954-1754-4342-9859-b56300b23da5](https://github.com/user-attachments/assets/cf24e65e-6e33-4e53-9f1e-852ce415453f)


## Server:
![360306819-710f4a1a-a835-4a3b-b534-1749f835c1c7](https://github.com/user-attachments/assets/2e7543fe-9ad9-49a3-bf10-b1fe9ddcd5b3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
