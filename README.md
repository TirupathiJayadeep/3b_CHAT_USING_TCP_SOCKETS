# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
### Client.PY
```
import socket
s=socket.socket()
s.bind(('localhost',8090))
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
### OUPUT
![image](https://github.com/user-attachments/assets/3fc190e0-f1d1-4306-a8fd-d86c2d47521d)

### Server.PY
```
import socket
s=socket.socket()
s.connect(('localhost',8090))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
### OUTPUT
![image](https://github.com/user-attachments/assets/b65dbaa5-51e4-4df0-934a-6477b76b7400)

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
