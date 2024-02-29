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
```
Name : JANANI.S
Reg no: 212222230049
```

### server code
```py
# echo-server.py
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```

### client code
```py
# echo-client.py

import socket

HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)

print(f"Received {data!r}")
```

## OUTPUT:
### Server side:

![ECHO](https://github.com/JananiSoundararajan/Echoserver/assets/119477549/debd2ba7-9852-4e12-9507-f7c72846d5fa)


### Client Side :

![ECHOS](https://github.com/JananiSoundararajan/Echoserver/assets/119477549/abfb0107-fb93-44a0-a239-32b277f04663)


## RESULT:
The program is executed successfully
