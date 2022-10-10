<h1> WEB PROXY CACHE</h1>


**ABOUT**

This project comprises of web-client and web-proxy in which HTTP message is sent from client to the proxy. The proxy checks it's cache to determine whether the request is stored or not. When the client sends HTTP request to the Web-proxy, a TCP socket is opened in which after a connection is made, the client's requested url is sent to the proxy. The proxy will then act as client by sending a request to a web server
to retreive the url. Here is a visualization of how the request travels:

Client -> Proxy Server -> Origin Server -> Proxy Server -> Client. 

**PYTHON MODULES USED**

This project uses modules: **binascii, socket, and sys, re**

NOTE: When choosing url to send to proxy, refrain from using **http://**. The code will crash and the proxy will not recognize the url.
![image](https://user-images.githubusercontent.com/68576099/193414680-fa994d3b-4172-4124-b87c-598d53e16434.png)

**LAUNCH**

To launch code, run the proxy server first and then run the client as shown below:
![image](https://user-images.githubusercontent.com/68576099/193414788-fb05f93c-6c7a-41ba-86a7-c01f6fa9e2d0.png)

This allows the proxy to listen for the client, antipciating when a request will be sent. 
![CodeScreenshot 2022-10-01 104723](https://user-images.githubusercontent.com/68576099/193415106-aa45e2d5-d716-4de5-a5ca-89d7ad1906fd.png)

**CACHE**
When checking whether request is stored in cache:
- After running proxy
- Execute client file
- Keep proxy running and run the client file again **with the same website requested from first execution**
- You should receive a 304 Not Modified response (this is saying that between the last time the client sent a request (bullet point 2) to the most recent client request (bullet point 3) nothing has changed. This response is possible becasue the the proxy checked it's cache. Therfore the cache is doing it's job. 
