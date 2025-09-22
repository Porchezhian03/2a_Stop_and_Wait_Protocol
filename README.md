# ExNo.2a_Stop_and_Wait_Protocol
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
```python
1.Client
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
```python
2.server
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT

1.Client
<img width="868" height="330" alt="{7D8DBE37-C60B-49D2-8643-F3EBB0F8F3F4}" src="https://github.com/user-attachments/assets/b13b3d30-2f99-4273-8128-606ebb3675ab" />


2.Server
<img width="901" height="327" alt="{8C71B325-42DB-4858-B814-F1B1983A7110}" src="https://github.com/user-attachments/assets/42e8b645-a5ea-4c6b-aa6f-d545b03f0274" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
