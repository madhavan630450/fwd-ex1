# EX01 Developing a Simple Webserver
## Date:27.03.2025
## Name:Marimuthu Mathavan
## Reg No:212224230153

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''<!doctype html>
<html>
<head>
<title>WEBSERVER</title>
<style>
    table,tr,td,th
    {
    
    border:1px solid #000000;
    border-collapse: separate;
    padding:10px;
    text-align:center;
    background-color: aquamarine;
    }
    </style>
</head>
<body>
<left><h1 style="font-family: 'Times New Roman', Times, serif;"><b><u>TCP/IP PROTOCOLS</u></b></h1><br>
</left>
<table>
<tr>
<th>S.NO</th>
<th>LAYER</th>
<th>PROTOCOLS</th>
</tr>
<tr>
    <td>1.</td>
    <td>Transport layer protocol</td>
    <td>TCP</td>
    
<tr>
<td>2.</td>
<td>Application layer protocol</td>
<td>HTTPS,FTP</td>
</tr>
    

    
</tr>
<tr>
    <td>3.</td>
    <td>Link layer protocol</td>
    <td>MAC</td>
    </tr>
    
<tr>
<td>4.</td>
<td>Internet layer protocol</td>
<td>IP</td>
</tr>
    

</table>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("My webserver is running") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()


## OUTPUT:
![alt text](<Screenshot (48).png>)
![alt text](<Screenshot (49).png>)
## RESULT:
The program for implementing simple webserver is executed successfully.

