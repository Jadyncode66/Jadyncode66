<h1> WEB PROXY CACHE</h1>


**ABOUT**

This project comprises of web-client and web-proxy in which HTTP message is sent from client to the proxy. The proxy checks it's cache to determine whether the request is stored or not. When the client sends HTTP request to the Web-proxy, a TCP socket is opened in which after a connection is made, the client's requested url is sent to the proxy. The proxy will then act as client by sending a request to a web server
to retreive the url. Here is a visualization of how the request travels:

Client -> Proxy Server -> Origin Server -> Proxy Server -> Client. 

**PYTHON MODULES USED**

This project uses modules: **binascii, socket, and sys, re**
**NOTE:** Test with websites beginning with **http://** NOT http**s**://.

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

***TESTING WITH WEB BROWSER***
Test your web proxy using a web browser as a client instead of the web client. To do this, choose your favourite browser and change
the proxy settings to use the web proxy listening on localhost:50007: i.e., to use your web proxy. If you are having trouble with this, you can go directly to your Settings on your laptop, search "Proxy" and follow the same instructions above. 

After Setting up Proxy on your laptop:
- Run the web proxy code
- Open new window in browser and type in the website you would like: (WITH HTTP://)
- The website will load and feel free to test with other sites
- YOU DO NOT NEED TO RUN THE CLIENT CODE. Here the browser is the acting client
- When you are finish testing, turn of the manual proxy you made.

**Disclaimer**: When you are testing out the web browser, you will see other connections in your terminal that indicate failure. Not to worry. When you enter your website, you will have to look amongst all the other connections for yours. I've encoperated print statements inroder that you can locate where the GET request for your website is. 
