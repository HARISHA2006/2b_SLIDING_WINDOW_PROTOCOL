# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
To write a python program to perform IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
CLIENT:
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
s.connect(('localhost',8000)
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
CLIENT:

![image](https://github.com/HARISHA2006/2b_SLIDING_WINDOW_PROTOCOL/assets/148843830/9b57338c-6411-47ea-9e8a-5d9527a051b8)

SERVER:

![image](https://github.com/HARISHA2006/2b_SLIDING_WINDOW_PROTOCOL/assets/148843830/435329b0-86b2-4121-bb44-e472aea59fc0)

## RESULT
Thus, python program to perform IMPLEMENTATION OF SLIDING WINDOW PROTOCOL was successfully executed
