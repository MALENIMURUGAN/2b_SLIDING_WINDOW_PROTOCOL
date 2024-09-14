# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: MALENI M
## REGISTER NO:212223040110
## AIM:
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
     while(i<len(l)):
          st+=s
          c.send(str(l[i:st]).encode())
          ack=c.recv(1024).decode()
          if ack:
              print(ack)
              i+=s
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
     print(s.recv(1024).decode())
     s.send("acknowledgement recived from the server".encode())
```
## OUTPUT:
CLIENT:

![image](https://github.com/user-attachments/assets/9e6533f6-5477-43e0-bd1e-41bb0ec12f25)

SERVER:

![image](https://github.com/user-attachments/assets/01611711-a7b4-4ebf-8b3c-061e2a4389cb)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
