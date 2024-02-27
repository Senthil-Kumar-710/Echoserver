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
![304289799-1cfbf389-38ec-46f9-8978-715c2475e6f2](https://github.com/Senthil-Kumar-710/demo/assets/93860256/162428a4-7d4a-4107-97ba-51b2a88c4dbc)

### echo-client.py
![304289870-e8f01a07-c716-414f-a5c3-452ddbe3b959](https://github.com/Senthil-Kumar-710/demo/assets/93860256/018cd658-14a8-4716-975e-cc3461262b98)


## RESULT:
The program is executed successfully.
