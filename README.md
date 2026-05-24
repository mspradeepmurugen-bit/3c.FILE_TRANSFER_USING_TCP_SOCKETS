# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
slient
```
import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
data = file.read() 
client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```
client
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
file.write(data) 
print("File received successfully") 
# Close connection 
client.close()
```
## OUPUT
<img width="1206" height="301" alt="Screenshot 2026-05-24 210728" src="https://github.com/user-attachments/assets/270f024f-3ad4-43fc-a175-7f1ba3f12aa6" />
<img width="910" height="277" alt="Screenshot 2026-05-24 210736" src="https://github.com/user-attachments/assets/306d7310-534d-4371-9817-925779c4a738" />
<img width="767" height="305" alt="Screenshot 2026-05-24 211306" src="https://github.com/user-attachments/assets/c9a8ffa5-d04e-43ee-9247-3619c789c55c" />
<img width="761" height="401" alt="Screenshot 2026-05-24 211314" src="https://github.com/user-attachments/assets/b9debb2f-0710-4a38-97c4-ddc25ba4c3d3" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
