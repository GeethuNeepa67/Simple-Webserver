# EX01 Developing a Simple Webserver
## Date:1/12/25

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
content ='''
<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Table</title>
    <style>
        body {
            font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(to right, #6a11cb, #2575fc);
            margin: 0;
            padding: 30px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        table {
            border-collapse: collapse;
            width: 80%;
            max-width: 900px;
            background-color: #ffffff;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.3);
        }
        caption {
            font-size: 28px;
            font-weight: bold;
            padding: 15px;
            background: #ff7eb3;
            color: white;
            letter-spacing: 1px;
        }
        th, td {
            border: 1px solid #ddd;
            text-align: center;
            padding: 15px;
        }
        th {
            background: #00c6ff;
            color: white;
            text-transform: uppercase;
            font-size: 16px;
            letter-spacing: 1px;
        }
        tr:nth-child(even) {
            background-color: #f2f8ff;
        }
        tr:hover {
            background-color: #ffeaa7;
            transform: scale(1.02);
            transition: 0.3s ease-in-out;
        }
    </style>
</head>
<body>

    <table>
        <caption>TCP/IP Protocol Layers</caption>
        <tr>
            <th>Layer</th>
            <th>Functions</th>
            <th>Examples</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>User interaction, data formatting, services</td>
            <td>HTTP, FTP, SMTP, DNS</td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>Reliable data transfer, flow control</td>
            <td>TCP, UDP</td>
        </tr>
        <tr>
            <td>Internet Layer</td>
            <td>Logical addressing, routing</td>
            <td>IP, ICMP, ARP</td>
        </tr>
        <tr>
            <td>Network Access Layer</td>
            <td>Physical addressing, data transmission</td>
            <td>Ethernet, Wi-Fi</td>
        </tr>
    </table>

</body>
</html>
```
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

## OUTPUT:
<img width="617" height="231" alt="Screenshot 2025-12-05 195449" src="https://github.com/user-attachments/assets/919f14db-6600-4520-b4cb-625b7327ec1e" />


## RESULT:
The program for implementing simple webserver is executed successfully.
