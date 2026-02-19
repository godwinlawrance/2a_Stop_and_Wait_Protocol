# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
Algorithm – Server Side

(1)Start

(2)Import the socket library.

(3)Create a socket using socket() function.

(4)Bind the socket to the local host and port number 8001.

(5)Put the socket into listening mode using listen().

(6)Accept a connection request from the client using accept().

(7)Repeat the following steps until communication ends:

(a)Read data from the user (frame).

(b)Send the data to the client using send().

(c)Wait for acknowledgement from the client using recv().

(d)If acknowledgement is received:

  •Display the acknowledgement.

  •Continue sending the next data.

(e)Else:

  •Close the connection.

  •Stop execution.

(8)Stop

Algorithm – Client Side 

(1)Start

(2)Import the socket library.

(3)Create a socket using socket() function.

(4)Connect the socket to the server using host name and port number 8001.

(5)Repeat the following steps:

   •Receive data (frame) from the server using recv().

   •Display the received data.

   •end acknowledgement to the server using send().

(6)Continue until the server closes the connection.

(7)Stop

## PROGRAM
## Server.py
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived from the server".encode())
```
## Client.py
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
## OUTPUT
<img width="1139" height="257" alt="image" src="https://github.com/user-attachments/assets/4f3d8858-d96a-4c81-9376-fe696a460ce0" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
