# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE:

AIM :


ALGORITHM :


PROGRAM :
Client:
~~~
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send:"))
l=list(range(size))
s=int(input("Enter Window Size:"))
st=0
i=0
while True:
	while(i<len(l)):
		st+=s
		c.send(str(l[i:st]).encode())
		ack=c.recv(1024).decode()
		if ack:
			print(ack)
			i+=s
~~~
Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
	print(s.recv(1024).decode())
	s.send("acknowledgement recieved from the server".encode())
~~~

OUTPUT :
![](https://github.com/RanjithD18/EX-2/blob/main/Screenshot%20from%202023-05-17%2021-17-23.png)


RESULT :



