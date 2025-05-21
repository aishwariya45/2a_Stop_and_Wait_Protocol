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
server
```
import socket 
s=socket.socket() 
s.connect(('localhost',8007)) 
while True: 
        print(s.recv(1024).decode()) 
        s.send("Acknowledgement Recived".encode()) 


```
client
```
import socket 
s=socket.socket() 
s.bind(('localhost',8007))
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
![image](https://github.com/user-attachments/assets/87776bb9-5823-42a7-bc23-7b4fa44399c2)
![Screenshot 2025-05-21 115708](https://github.com/user-attachments/assets/e3f7a270-ce97-4b36-971f-77299db3e53b)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
