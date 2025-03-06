# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
Name : Akshaya R

Reg no :212223220005

CLIENT
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("client > ")
    s.send(msg.encode())
    if msg == 'exit': 
        print("Closing connection...")
        break
    print("server > ", s.recv(1024).decode()) 
s.close()
print("Client closed.")
```

SERVER
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server is listening...")
c, addr = s.accept()
print(f"Connection from {addr} has been established.")
while True:
    s_msg = c.recv(1024).decode()
    if s_msg == 'exit':
        print("Client requested to close the connection.")
        break
    print("client > ", s_msg)
    c.send(s_msg.encode())
c.close()
s.close()
print("Server closed.")


```

## OUTPUT:
![Screenshot 2025-03-06 114110](https://github.com/user-attachments/assets/2b406732-20b2-490e-b3df-a2dbdc274ac7)


## RESULT:
The program is executed successfully
