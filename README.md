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
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<!doctype html>
<html>
    <head>
      <title> My Web Server</title>
    </head>
    <body>
        <table border="1" align="center" cellpadding="10" bgcolor="pink" >
        <caption><h1>List Of Protocols in TCP/IP Protocol Suite</h1></caption>
        <tr>
            <th>S.No.</th><th>Name Of The Layer</th><th>Name of The Protocol</th>
        </tr>
        <tr>
            <td>1.</td><td>Application Layer</td><td>HTTP,FTP,DNS,TELNET & SSH</td>
        </tr>
        <tr>
            <td>2.</td><td>Transport Layer</td><td>TCP & UDP</td>
        </tr>
        <tr>
            <td>3.</td><td>Network Layer</td><td>IPV4/IPV6</td>
        </tr>
        <tr>
            <td>4.</td><td>Link Layer</td><td>Ethernet</td>
        </tr>
        </table>
    </body>
</html>'''


    
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address=('',8000)
httpd=HTTPServer(server_address,MyServer)
httpd.serve_forever()

```


## OUTPUT:

<img width="1732" height="980" alt="Screenshot 2025-09-06 091251" src="https://github.com/user-attachments/assets/40852f07-800d-4d69-a2cd-18d4d3a9df0a" />

## RESULT:
The program for implementing simple webserver is executed successfully.
