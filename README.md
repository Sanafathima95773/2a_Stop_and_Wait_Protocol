# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recived".encode())
```

## OUTPUT
client output:
![image](https://github.com/Sanafathima95773/2a_Stop_and_Wait_Protocol/assets/147084627/91cb864e-f76b-4126-9144-fc0f8dc9be9f)
server output:
![image](https://github.com/Sanafathima95773/2a_Stop_and_Wait_Protocol/assets/147084627/98fd91a6-107b-482f-96e9-eb99dde2dafc)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
