# EX01 Developing a Simple Webserver
## Date: 15-04-2025

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
from http.server import BaseHTTPRequestHandler, HTTPServer

class MyHandler(BaseHTTPRequestHandler):
    html_content = """
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>System Information</title>
      <style>
        body {
          font-family: Arial, sans-serif;
          background-color: #f4f4f9;
          margin: 0;
          padding: 0;
          display: flex;
          justify-content: center;
          align-items: center;
          height: 100vh;
        }

        .container {
          background: #fff;
          padding: 20px;
          border-radius: 8px;
          box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
          max-width: 400px;
          width: 100%;
        }

        .title {
          font-size: 1.5rem;
          font-weight: bold;
          margin-bottom: 20px;
          text-align: center;
          color: #333;
        }

        .info {
          margin-bottom: 15px;
          padding: 10px;
          background: #f9f9f9;
          border-radius: 6px;
          box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
        }

        .info span {
          font-weight: bold;
          color: #555;
        }
      </style>
    </head>
    <body>
      <div class="container">
        <div class="title">System Information</div>
        <div class="info"><span>Device Name:</span> DESKTOP-5DTLKRH</div>
        <div class="info"><span>Processor:</span> 13th Gen Intel(R) Core(TM) i5-1335U 1.30 GHz</div>
        <div class="info"><span>Installed RAM:</span> 16.0 GB (15.7 GB usable)</div>
        <div class="info"><span>Device ID:</span> C41CBE44-B2F0-4735-99DB-38B443360259</div>
        <div class="info"><span>Product ID:</span> 00342-42709-00703-AAOEM</div>
        <div class="info"><span>System Type:</span> 64-bit operating system, x64-based processor</div>
        <div class="info"><span>Pen and Touch:</span> No pen or touch input is available for this display</div>
      </div>
    </body>
    </html>
    """

    def do_GET(self):
        # Handle GET requests
        print("Request received")
        self.send_response(200)
        self.send_header('Content-Type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(self.html_content.encode())

# Define server address and port
server_address = ('', 8000)  # Host on all available IPs, port 8000
httpd = HTTPServer(server_address, MyHandler)

print("My webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![Screenshot 2024-12-07 155807](https://github.com/user-attachments/assets/f8651017-83ac-4a3f-8346-49b888ad988b)

![Screenshot 2024-12-07 155829](https://github.com/user-attachments/assets/ead14cf0-e085-448c-af6f-f491cd3aa24a)


## RESULT:
The program for implementing simple webserver is executed successfully.
