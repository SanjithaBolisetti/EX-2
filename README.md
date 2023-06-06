# IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# EXP: 2

# DATE:15-03-2023

# AIM :
To write a python program to perform stop and wait protocol

# ALGORITHM :
1. . Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program

# CLIENT PROGRAM :
```import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
 ```

# SERVER PROGRAM :
```import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())
```
# SERVER OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2/assets/119393633/95aed9a1-8b0c-4945-b6c5-1460abbedf2b)

# CLIENT OUTPUT:
![image](https://github.com/SanjithaBolisetti/EX-2/assets/119393633/70b52a1b-f585-43b2-96a2-8b79a070f586)

# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
