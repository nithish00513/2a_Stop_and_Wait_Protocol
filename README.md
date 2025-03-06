![371231188-33def1d8-0992-4b65-b6f6-899453ba5bcc](https://github.com/user-attachments/assets/b6f83d02-53a2-466b-9c07-e0a4caa4e72f)# 2a_Stop_and_Wait_Protocol
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
## client.py
~~~
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
~~~

## server.py
~~~
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
~~
## OUTPUT
![371231188-33def1d8-0992-4b65-b6f6-899453ba5bcc](https://github.com/user-attachments/assets/7a0a2a40-3672-4321-b3cb-672eb87099be)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
