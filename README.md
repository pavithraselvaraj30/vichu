# EX01 Developing a Simple Webserver
## Date:14/3/24

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
from http.server import HTTPServer,BaseHTTPRequestHandler
content = """
<html>
     <title> Image Map </title>
     <body>
          <table border = "2" cellspacing = "10" cellpading = "6">
               <caption> Top five revenue generating software companies</caption>
               <tr>
                    <th>S.no</th>
                    <th>Company</th>
                    <th>Revenue</th>
               </tr>
               <tr>
                    <td>1</td>
                    <td>Qualcomm</td>
                    <td>9.548</td>
               </tr>
               <tr>
                    <td>2</td>
                    <td>NVIDIA</td>
                    <td>7.904</td>
               </tr>
               <tr>
                    <td>3</td>
                    <td>Broadcom</td>
                    <td>6.110</td>
               </tr>
               <tr>
                    <td>4</td>
                    <td>AMD</td>
                    <td>5.887</td>
               </tr>
               <tr>
                    <td>5</td>
                    <td>Marvell</td>
                    <td>1.412</td>
               </tr> 
          </table>
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
![alt text](<Screenshot 2024-03-22 100334.png>)
![alt text](<Screenshot 2024-03-22 100349.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
