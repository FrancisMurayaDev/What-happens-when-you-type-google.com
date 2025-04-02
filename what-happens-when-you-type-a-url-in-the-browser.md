#  What happens when you type a URL in the browser.

When you type a url such as `https://www.google.com` in the browser, various things happen before getting any output on the browser. 

#### 1. The computer sends a request the nomain name system (DNS).

The DNS serves as an adddress for all domain names.

It sends back the exact IP address of the server in which `https://www.google.com` points to.

#### 2. Knowing the IP, the computer establishes a connection with the server through the IP address. 

This type of connection is known as Transmission Control Protocol (TCP) and the computer is able to establish this connection through the Internet Protocol (IP).

This process is known as a `HandShake`.

#### 3. If your computer is behind a firewall, the computer checks to ensure that the particular request that you are making is allowed before permiting it. 

Also, if the server you are trying to access is behind a firewall, a similar check is done before you are finally able to connet to the server. 

#### 4. After establishing the connection, the browser now sends a request for the webpage using an encryption protocol such as Secure Sockets Layer (SSL) or Transport Layer Security (TLS).

They help encrypt the data that is shared between your computer and the server. 

This type of conection is what is responsible for the `s` in `https` which also implies that the connection is secure. 

#### 5. In our case, a browser like Google usually has a high traffic. 

Google maintains a host of servers for that. 

They have a load balancer that recieves most of the requests and sends them to a particular server. 

The request from your browser will hit the load balancer first, which will forward it to a specific server depending on the algorithim used by the load balancer. 

#### 6. The server that recieves the request then sends a response back to the load balancer which also forwards the response back to your browser. 

This response will mostly include html, css and JavaScript files that make up google's homepage. 

#### 7. The HTML file returned tell the browser how to render the content of the page.

The CSS files tell the browser how to style the content. 

The JavaScript files add interactivity to the page. 

#### 8. If there is need for some dynamic content such as Google Search results.

The webserver will make a request to the application server which in turn may make a request to a database server to get some data and send it back to the web server. 

The webserver will then include this in the response that it sends back to the browser. 

#### 9. Finally the browser will render the page and display it to you. 

# Lets Dive More into What Happens: 






