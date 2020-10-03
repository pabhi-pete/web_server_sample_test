# web_server_sample_test
you will learn the basics of socket programming for TCP connections in Python: how to create
a socket, bind it to a specific address and port, as well as send and receive a HTTP packet. You will also
learn some basics of HTTP header format. To develop a web server that handles one HTTP request at a time. 
<h2>Conditions<h2>
The web server should accept and parse the HTTP request, get the requested file from the server’s file system, create an HTTP response message consisting of the requested file preceded by header lines, and then send the response directly to the client. If the requested file is not present in the server, the server should send an HTTP “404 Not
Found” message back to the client.
Code: 
  Below you will find the skeleton code for the Web server. You are to complete the skeleton code. The
places where you need to fill in code are marked with #Fill in start and #Fill in end. Each place
may require one or more lines of code. 
#import socket module
from socket import *
import sys # In order to terminate the program
serverSocket = socket(AF_INET, SOCK_STREAM)
#Prepare a sever socket
#Fill in start
#Fill in end
while True:
 #Establish the connection
 print('Ready to serve...')
 connectionSocket, addr = #Fill in start #Fill in end
 try:
 message = #Fill in start #Fill in end
 filename = message.split()[1]
 f = open(filename[1:])
 outputdata = #Fill in start #Fill in end
 #Send one HTTP header line into socket
 #Fill in start
 #Fill in end
 #Send the content of the requested file to the client
 for i in range(0, len(outputdata)):
 connectionSocket.send(outputdata[i].encode())
 connectionSocket.send("\r\n".encode())

 connectionSocket.close()
 except IOError:
 #Send response message for file not found
 #Fill in start 
 #Fill in end
 #Close client socket
 #Fill in start
 #Fill in end
serverSocket.close()
sys.exit()#Terminate the program after sending the corresponding data 
