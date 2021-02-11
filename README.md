# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
## mywebserver.py
~~~
from http.server import HTTPServer,BaseHTTPRequestHandler

Content="""
<!doctype html>
<html lang="en">
<head>
<title>my webserver</title>
</head>
<body>
<h1>MULTIPLICATION TABLES OF 9</h1>
9×0=0<br>
9×1=9<br>
9×2=18<br>
9×3=27<br>
9×4=36<br>
9×5=45<br>
9×6=54<br>
9×7=63<br>
9×8=72<br>
9×9=81<br>
9×10=90<br>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recived")

        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')             
        self.end_headers()

     #to send the responce
        self.wfile.write(Content.encode())

 #to create server address     
server_address=('',80)

#to listen at the specified port
httpd = HTTPServer(server_address,myhandler)
print("MY WEBSERVER IS RUNNING...")
httpd.serve_forever()
~~~
## OUTPUT:

![output](./static/img/s.png)

![output](./static/img/w.png)

## RESULT:
Thus, a webserver is designed to display multiplication table and is hosted in the URL
http://prashethaa.student.saveetha.in/