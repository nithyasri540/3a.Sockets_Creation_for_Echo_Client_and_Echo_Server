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
###SERVER 
```

import socket

# Create socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind the socket with host and port
host = '127.0.0.1'
port = 5000
server_socket.bind((host, port))

# Listen for incoming connections
server_socket.listen(1)
print("Echo Server is waiting for connection...")

# Accept client connection
client_socket, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    # Receive message from client
    data = client_socket.recv(1024).decode()

    if not data:
        break

    print("Client:", data)

    # Send same message back to client
    client_socket.send(data.encode())

# Close sockets
client_socket.close()
server_socket.close()
```
### Client 
```

import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

host = '127.0.0.1'
port = 5000

# Connect to server
client_socket.connect((host, port))

print("Connected to Echo Server")

while True:
    message = input("Enter message: ")

    if message.lower() == 'exit':
        break

    client_socket.send(message.encode())

    data = client_socket.recv(1024).decode()

    print("Echo from Server:", data)

client_socket.close()
```
## OUPUT
<img width="1512" height="192" alt="Screenshot 2026-11-18 100901" src="https://github.com/user-attachments/assets/1653fcd8-1bfb-4634-b932-9d58610f2ee8" />
<img width="1512" height="192" alt="Screenshot 2026-11-18 100901" src="https://github.com/user-attachments/assets/2c0f2e6e-fea3-481c-9b39-3e873cfb9602" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
