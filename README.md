# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>
```
client.py
```
s = socket.socket() s.connect(('localhost', 8000))

while True: ip = input("Enter the website you want to ping (or type 'exit' to quit): ") s.send(ip.encode('utf-8')) if ip.lower() == 'exit': break print(s.recv(4096).decode('utf-8'))

s.close()

server.py
```
import socket from pythonping import ping

s = socket.socket() s.bind(('localhost', 8000)) s.listen(5) print("Server listening on port 8000...") c, addr = s.accept() print(f"Connection from {addr}")

while True: try: hostname = c.recv(1024).decode('utf-8') if not hostname or hostname.lower() == 'exit': print("Client disconnected.") break response = ping(hostname, verbose=False, count=4) c.send(str(response).encode('utf-8')) except Exception as e: c.send(f"Ping failed: {e}".encode('utf-8'))

c.close()
```

## Output

<img width="661" height="110" alt="Screenshot 2026-08-21 140824" src="https://github.com/user-attachments/assets/6ea2467f-5166-4642-b59c-293d98ae29e2" />

<img width="713" height="351" alt="Screenshot 2026-08-21 140732" src="https://github.com/user-attachments/assets/393a4c7c-58b6-4e6d-91c8-67920d98f412" />

## Result
Thus Execution of Network commands Performed 
