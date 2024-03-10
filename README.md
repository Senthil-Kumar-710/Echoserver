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

### echo-server.py:
```

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

### echo-client.py
```
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
### echo-server.py:

![eht1](https://github.com/Senthil-Kumar-710/Echoserver/assets/93860256/3c1db2e7-adc8-4b0a-ab39-455e478c3e05)

### echo-client.py

![eht2](https://github.com/Senthil-Kumar-710/Echoserver/assets/93860256/6fd65756-fbcb-4a1f-9650-32be1b87db56)


## RESULT:
The program is executed successfully.
