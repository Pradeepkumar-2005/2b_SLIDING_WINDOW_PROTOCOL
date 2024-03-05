# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
To write a python program to perform sliding window protocol

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
# Cilent
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
#Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```

## OUTPUT
# Cilent
![309001059-f179f925-f406-4648-9351-a171b8872b19](https://github.com/Pradeepkumar-2005/2b_SLIDING_WINDOW_PROTOCOL/assets/147474038/6c78b228-0e6f-41a5-94dd-8636e547131a)

# Server
![309001170-d9cb6a95-e50a-4f75-b739-e2eef0c6cae1](https://github.com/Pradeepkumar-2005/2b_SLIDING_WINDOW_PROTOCOL/assets/147474038/d42522b9-ffe4-40dc-a60f-4966e9c43314)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
