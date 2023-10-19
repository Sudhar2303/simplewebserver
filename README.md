# EX01 Developing a Simple Webserver
## Date: 19/09/2023

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
  <head>
     <title>Simple WebServer</title>
  </head>
  <body>
    <ul>
        <li>IBM</li>
        <li>AMAZON</li>
        <li>TCS</li>
        <li>CORGIZANT</li>
        <li>INFOSYS</li>
      </ul>
  </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![Alt text](<sudhar/ex1/static/Screenshot (288).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
