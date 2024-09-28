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
### client ARP:
```
NAME: MOHAMED HAMEEM SAJITH J
REG NO: 212223240090

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
### SERVER ARP:

```
NAME: MOHAMED HAMEEM SAJITH J
REG NO: 212223240090

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical address: ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())

```
## OUPUT - ARP :

![WhatsApp Image 2024-09-28 at 09 19 15_a48afcd0](https://github.com/user-attachments/assets/b57f9251-32ad-4dd7-8ece-d2b950c95fcf)


## PROGRAM - RARP :

### client RARP:
```
NAME: MOHAMED HAMEEM SAJITH J
REG NO: 212223240090

import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not found".encode())
```
### SERVER RARP:

```
NAME: MOHAMED HAMEEM SAJITH J
REG NO: 212223240090

import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
    ip=input("Enter mac address: ")
    s.send(ip.encode())
    print("Logical address",s.recv(1024).decode())

```

## OUPUT -RARP :

![WhatsApp Image 2024-09-28 at 09 23 08_e4f91166](https://github.com/user-attachments/assets/f56d0ab0-7919-4929-aa28-90f5dcff1040)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
