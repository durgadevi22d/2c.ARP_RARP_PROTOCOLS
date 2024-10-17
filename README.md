# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"192.168.208.205":"E0-2E-0B-38-3F-3D"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except keyError:
        c.send("Not Found".encode())
```

## PROGRAM - RARP
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter Logical Address:")
    s.send(ip.encode())
    print("MAC address",s.recv(1024).decode())

```
## OUTPUT:
![cn exp 2c op](https://github.com/user-attachments/assets/0e67ae26-5536-4829-9198-3079bbc6ea8f)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
