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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1> Top 5 programming language</h1>
<h2>1.Python</h2>
<h3> Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level built in data structures, combined
with dynamic typing and dynamic binding, make it very attractive for Rapid Application Development, as well as for use as a scripting or glue language
to connect existing components together. Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program
maintenance. Python supports modules and packages, which encourages program modularity and code reuse. The Python interpreter and the extensive
standard library are available in source or binary form without charge for all major platforms, and can be freely distributed.</h3>
<h2>2.C</h2>
<h3>C was originally developed at Bell Labs by Dennis Ritchie between 1972 and 1973 to construct utilities running on Unix. It was applied to 
re-implementing the kernel of the Unix operating system. During the 1980s, C gradually gained popularity. It has become one of the most widely used 
programming languages, with C compilers from various vendors available for the majority of existing computer architectures and operating systems. 
C has been standardized by ANSI since 1989 and by the International Organization for Standardization.</h3>
<h2>3.Swift</h2>
<h3> Swift is a powerful and intuitive programming language for iOS, iPadOS, macOS, tvOS, and watchOS. Writing Swift code is interactive and fun, the
syntax is concise yet expressive, and Swift includes modern features developers love. Swift code is safe by design, yet also produces software that runs 
lightning-fast. Swift is the result of the latest research on programming languages, combined with decades of experience building Apple platforms. Named
parameters are expressed in a clean syntax that makes APIs in Swift even easier to read and maintain. Even better, you don’t even need to type semi-colons.
Inferred types make code cleaner and less prone to mistakes, while modules eliminate headers and provide namespaces. To best support international languages
and emoji, Strings are Unicode-correct and use a UTF-8 based encoding to optimize performance for a wide-variety of use cases. Memory is managed automatically
using tight, deterministic reference counting, keeping memory usage to a minimum without the overhead of garbage collection.</h3>
<h2>4.Java</h2>
<h3>Java is a programming language and computing platform first released by Sun Microsystems in 1995. It has evolved from humble beginnings to power a large share
of today’s digital world, by providing the reliable platform upon which many services and applications are built. New, innovative products and digital services
designed for the future continue to rely on Java, as well.</h3>
<h2>5.Java Script</h2>
<h3>JavaScript is a scripting or programming language that allows you to implement complex features on web pages — every time a web page does more than just sit
there and display static information for you to look at — displaying timely content updates, interactive maps, animated 2D/3D graphics, scrolling video jukeboxes, etc.
— you can bet that JavaScript is probably involved. It is the third layer of the layer cake of standard web technologies, two of which (HTML and CSS) we have covered in
 much more detail in other parts of the Learning Area.</h3>

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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running")
httpd.serve_forever()

## OUTPUT:
Server side output:
![image](https://user-images.githubusercontent.com/94164665/143048942-88c4624e-941c-47af-a644-3c050a96b521.png)
Clint side output: 
![image](https://user-images.githubusercontent.com/94164665/143049016-29612f41-4968-4d28-a6be-ca3d87dd172f.png)


## RESULT:
The web develop program is successfully shows top 5 programming languages. 
