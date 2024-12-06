# EX01 Developing a Simple Webserver

# Date:6-12-2024
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
```from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
    <title>Device Specifications</title>
    <style>
        body {
            font-family:Georgia, 'Times New Roman', Times, serif;
            margin: 20px;
            background-color:blueviolet;
        }
        table {
            width: 60%;
            border-collapse: collapse;
            margin: 20px auto;
            background: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        th, td {
            text-align: left;
            padding: 12px;
            border: 1px solid #ddd;
        }
        th {
            background-color: #0078D7;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        tr:hover {
            background-color: #f1f1f1;
        }
        caption {
            font-size: 20px;
            font-weight: bold;
            padding: 10px;
            text-align: center;
        }
    </style>
</head>
<body>
    <table>
        <caption>Device Specifications</caption>
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>deepika</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>13th Gen intel(R)Core(TM)i5-1335U 1.30 GHz</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>16.0GB(15.7 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00342-42708-27260-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
```

# OUTPUT:
![saradeepika](https://github.com/user-attachments/assets/8587fa79-40dc-4d79-bd64-9b61f160f454)

![Screenshot (44)](https://github.com/user-attachments/assets/da2ab23f-c76b-4bce-85e6-3245ad6bbc46)


# RESULT:
The program for implementing simple webserver is executed successfully.
