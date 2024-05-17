# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
## client:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
  s.bind((HOST, PORT))
  s.listen()
  conn, addr = s.accept()
  with conn:
    print('Connected by', addr)
    while True:
      data = conn.recv(1024)
      if not data:
        break
      conn.sendall(data)
```
## server:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
   s.connect((HOST, PORT))
   while True:
      message = input("Enter message to send to server: ")
      s.sendall(message.encode())
      data = s.recv(1024)
      print('Received', repr(data.decode()))
```
## OUPUT
## client:
![321734735-120c605c-6dd7-4303-8715-c48d3797b290](https://github.com/Rithviknathan/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/148410509/11ea9b67-df7b-402d-9901-804198cf9e26)
## server:
![321734808-ce82cb7e-a0f2-4ca8-83b9-f1d1a86a1e11](https://github.com/Rithviknathan/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/148410509/e3f812ac-699e-40be-8c09-8cc572ea2f99)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
