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
## client
```python
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
## server
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
## client.py

<img width="742" height="237" alt="Screenshot 2025-10-09 055155" src="https://github.com/user-attachments/assets/758c6f45-4590-481e-9c85-71ba23426255" />

## Server.py

<img width="875" height="223" alt="Screenshot 2025-10-09 055143" src="https://github.com/user-attachments/assets/e4610989-e198-4f49-b645-b8d857a655b1" />
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
