# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

## DATE :6.3.2023

## AIM :
To write a python program to perform client server model.
## ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program

## CLIENT PROGRAM :
```
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break
 ````   
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
  ````
## SERVER OUTPUT :
![Screenshot from 2023-05-15 09-29-01](https://github.com/yogeshrao05/19CS406-EX-1/assets/122008288/fb977b90-8655-4046-93b6-1e77f9963409)

## CLIENT OUTPUT :
![Screenshot from 2023-05-15 09-29-10](https://github.com/yogeshrao05/19CS406-EX-1/assets/122008288/6d9f6950-0dc8-4e33-b2a1-bbd71561677e)


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
