# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# Name :Navinkumar v
# Reg no:212223230141
## AIM
To perform a study on sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### client:
```
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
### server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### client:
![Screenshot 2024-05-09 132709](https://github.com/navinofficial/2b_SLIDING_WINDOW_PROTOCOL/assets/151710204/e0b4de8f-8c26-40f4-9646-099d23c09778)
### server:
![image](https://github.com/navinofficial/2b_SLIDING_WINDOW_PROTOCOL/assets/151710204/b3f5df3e-3d7c-4392-9050-beb33e9b5740)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
