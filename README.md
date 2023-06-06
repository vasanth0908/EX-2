# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE:15-03-2023
AIM :
To write a python program to perform stop and wait protocol
ALGORITHM :
1. . Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.

6. Stop the program
CLIENT PROGRAM :
import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
SERVER PROGRAM :
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())
OUTPUT :
![1](https://github.com/vasanth0908/EX-2/assets/122000018/67fa77d8-d185-48d3-86fc-3d74660969e3)

![2](https://github.com/vasanth0908/EX-2/assets/122000018/7f7876af-8c3d-44c0-9573-a15de2cc017f)




RESULT :
IMPLEMENTATION OF STOP AND WAIT PROTOCOL AS BEEN EXCUTED SUCCESSFULLY



