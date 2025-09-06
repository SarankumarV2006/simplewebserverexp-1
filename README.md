# EX01 Developing a Simple Webserver
##Name:V.Sarankumar
#reg.no:212224220089
## Date: 30.08.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Experiment-1</title>
</head>
<body style="background-color: beige;text-align: center;color:blue; font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;font-size: medium;">
    <h1 style="background-color: blanchedalmond;color:burlywood;font-weight: 200;font-size:xx-large;">List Of Protocols In TCP/IP Model</h1>
     <h2 style="background-color:blanchedalmond;">Application Layer : HTTP,FTP,DNS,Telnet<br>
         Transport Layer : TCP & UDP<br>
        Network Layer: IPV4/IPV6<br>
        Link Layer : Ethernet</h2>
</body>
</html>'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


## OUTPUT:
<img width="1095" height="416" alt="Screenshot 2025-09-06 083705" src="https://github.com/user-attachments/assets/67a3f060-dc3f-41a3-9aae-e72588e134a5" />

<img width="1270" height="569" alt="Screenshot 2025-09-06 083645" src="https://github.com/user-attachments/assets/b765c065-0b13-41b0-8cff-52c4de594511" />

## RESULT:
The program for implementing simple webserver is executed successfully.
