# 2a_Stop_and_Wait_Protocol
## Name: Gowtham N
## Reg no: 212222220013
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
## client:
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
## client :
![image](https://github.com/user-attachments/assets/f81aa08a-b95f-456b-9c7a-67f05162b1a8)

## Server:
![image](https://github.com/user-attachments/assets/31b89134-290a-494b-a092-7e6885a52900)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
