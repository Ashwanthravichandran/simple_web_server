# EX01 Developing a Simple Webserver

# Date:27-11-2024
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
	<body bgcolor="yellow">
		<br>
<h1 align=" center">
Laptop Properties [ASHWANTH (24900175)]
</h1>
<br>
<br>
<center>
<form>
	<table border="2" cellpadding="2" cellspacing="2">
	<tr>
		<td><b> Device name: </b></td>
		<td>ASHWANTH</td> 
	</tr>
	<tr >
		<td><b> Processor: </b></td>
		<td>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</td>
	</tr>
	<tr >
		<td><b> Installed RAM: </b></td>
		<td>16.0 GB (15.7 GB usable)</td> 
	</tr>
	<tr>
		<td><b> Device ID: </b></td>
		<td> 15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
	</tr>
	<tr >
		<td><b> Product ID: </b> </td>
		<td>00342-42708-86861-AAOEM</td>
	</tr>
	<tr >
		<td><b> System type: </b></td>
		<td> 64-bit operating system, x64-based processor</td>
	</tr>
	<tr >
		<td><b> Pen and touch: </b> </td>
		<td>No pen or touch input is available for this display</td>
	</tr>
</table>
</form>
</center>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```




# OUTPUT:
![alt text](<Screenshot (5).png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
