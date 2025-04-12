# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
To write a python program to perform sliding window protocol 

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
 ## CLIENT 
import socket <br>
s=socket.socket() <br>
s.bind(('localhost',8000)) <br>
s.listen(5) <br>
c,addr=s.accept() 
size=int(input("Enter number of frames to send : "))<br>
l=list(range(size)) <br>
s=int(input("Enter Window Size : ")) <br>
st=0 <br>
i=0 <br>
while True: 
    while(i<len(l)): 
            st+=s         
            c.send(str(l[i:st]).encode())          
            ack=c.recv(1024).decode()         
            if ack:            
                print(ack)               
                i+=s
 ## SERVER
  
import socket <br>
s=socket.socket() <br>
s.connect(('localhost',8000)) <br>
while True:    <br>

    print(s.recv(1024).decode()) <br>
    
    s.send("acknowledgement recived from the server".encode())  <br>
    
## OUPUT
![Screenshot (416)](https://github.com/user-attachments/assets/bb8bc4f7-b1ab-488f-b782-20853968e49e)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
