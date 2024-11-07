# 2a_Stop_and_Wait_Protocol
NAME: DHANUSHA K
REG NO: 212223040034
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
## CLIENT
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
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## CLIENT
![Screenshot 2024-08-27 093649](https://github.com/user-attachments/assets/d0d4ee32-20d8-4620-bf75-0b4b36e2e1f2)
## SERVER
![Screenshot 2024-08-27 093545](https://github.com/user-attachments/assets/0bcaa073-8ba9-4af1-ab73-e090237542af)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
