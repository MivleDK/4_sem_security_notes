# OWASP top ten notes
Notes for security course taken Q1-Q2 2021 @ CPHBusiness, Lyngby


### [Severity 1] **Injection**

SQL and Command injection via. input fields.

**Defence**
- Using an allow list ie. comparing the input to a list of safe input/characters.
- Stripping input ie. removing bad chars before processing.

### [Severity 1] **OS Command injection**
Command Injection occurs when server-side code (like PHP) in a web application makes a system call on the hosting machine.  
It is a web vulnerability that allows an attacker to take advantage of that made system call to execute operating system commands on the server.  
Sometimes this won't always end in something malicious, like a `whoami` or just reading of files.  

The worst thing they could do would be to spawn a reverse shell to become the user that the web server is running as.  
A simple `;nc -e /bin/bash` is all that's needed and they own your server.

tl;dr An input field on a webpage for executing terminal commands on the server. This can be exploited if not secured.

### [Severity 2] **Broken Authentication**