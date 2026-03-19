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
1. sever.py
```
import socket

# Create socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind
host = '127.0.0.1'
port = 12345
server_socket.bind((host, port))

# Listen
server_socket.listen(1)
print("Echo Server is waiting for connection...")

# Accept connection
conn, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    # Receive message
    data = conn.recv(1024).decode()
    
    if not data:
        break
    
    print("Client:", data)
    
    # Echo back same message
    conn.send(data.encode())

# Close connection
conn.close()
server_socket.close()
```
2. client.py
```
import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
host = '127.0.0.1'
port = 12345
client_socket.connect((host, port))

while True:
    # Take input from user
    msg = input("Enter message: ")
    
    if msg.lower() == 'exit':
        break
    
    # Send message
    client_socket.send(msg.encode())
    
    # Receive echo
    data = client_socket.recv(1024).decode()
    print("Echo from server:", data)

# Close connection
client_socket.close()
```
## OUPUT
<img width="1047" height="139" alt="image" src="https://github.com/user-attachments/assets/6fdbd7a3-4e5d-4a5a-bfff-1baa9d82561b" />

<img width="1065" height="151" alt="image" src="https://github.com/user-attachments/assets/98d604ac-92a2-4f93-8079-bdf01178420a" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
