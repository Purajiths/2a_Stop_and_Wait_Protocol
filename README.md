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
## CLIENT:
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
![WhatsApp Image 2024-05-10 at 11 49 30_536032e0](https://github.com/Purajiths/2a_Stop_and_Wait_Protocol/assets/145548193/677b8da7-0e17-4e6a-8cd3-ab9068c560e0)

![WhatsApp Image 2024-05-10 at 11 49 33_64bbff76](https://github.com/Purajiths/2a_Stop_and_Wait_Protocol/assets/145548193/953cc661-b4da-42bb-9ed7-85c26f8e7934)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
