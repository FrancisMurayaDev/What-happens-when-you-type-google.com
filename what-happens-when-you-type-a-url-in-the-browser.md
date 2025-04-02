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

## DNS Request

When you use a browser to access any website or domain name, the browser stores the websites/domain information in its cache `(DNS record)`.

- If you type a domain name such as `google.com` in your browser, the browser checks if there is a recent `DNS record/cache` for that domain. 

- If there is one, it will use the `IP address` in the cache to send a request to the server. 

- This speeds up the process of ressolving the `domain name` to an `ip address` since it avoid the need to send a request to the `DNS server` to ressolve the domain name to an IP address.

This is a whole process on its own, here are the various steps involved. 

### DNS look Up Process

1. The browser sends a request to the local DNS resolver, which is usually provided by the internet service provider (ISP).

2. The local DNS resolver checks its cache to see if it has a recent copy of the DNS record for the domain. If it does, it sends the IP address back to the browser.

3. If the local DNS resolver does not have a recent copy of the DNS record, it sends a request to a root nameserver.

4. The root nameserver responds with the address of a top-level domain (TLD) nameserver, such as .com or .org.

5. The local DNS resolver sends a request to the TLD nameserver.

6. The TLD nameserver responds with the address of the authoritative nameserver for the domain.

7. The local DNS resolver sends a request to the authoritative nameserver.

8. The authoritative nameserver responds with the IP address for the domain.

9. The local DNS resolver sends the IP address back to the browser.

10. The browser sends a request to the server at the IP address to retrieve the webpage.

Additional steps may be involved if the DNS record is not found at any of the name servers, or if the DNS record has been configured to use a service such as `DNS load balancing` or `Content Delivery Networks (CDN)`.

- Once the IP address has been ressolved, it is cached by the local DNS ressolver and the browser so that future requests for the same domain name can be ressolved more quickly. 

- The length of time that the DNS record is cached `(the "TTL," or Time To Live)` is determined by the authoritative nameserver and can be configured by the domain owner.


### TCP/IP Connection 

TCP (Transmission Control Protocol) and IP (Internet Protocol) are two of the main protocols that make up the internet.

They work together to establish a connection between a client and a server and facilitate the transmission of data between them.

When you enter `"google.com"` into a web browser, the browser uses TCP/IP to establish a connection with the server that hosts the website.

#### Here is a more detail of what happens::

1. The browser sends a request to the server using IP to establish a connection.

2. The server receives the request and sends back a message acknowledging the request to establish a connection. This is the `handshake` process.

3. Once the handshake is complete, the browser can send a request for the webpage it wants to access (in this case, the homepage of google.com). 
- This request is sent using TCP, which ensures that the request is transmitted reliably and in the correct order.

4. The server receives the request and sends back the HTML code for the homepage of google.com to the browser. 
- This response is also sent using TCP to ensure reliable transmission.

5. The browser receives the HTML code and uses it to render the webpage on your screen. 
- Any resources (such as images) that the webpage needs are also requested and received using `TCP/IP`.

### Firewall

A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. 
- Its primary purpose is to protect a network from external threats, such as hackers and malware.

When you type a URL like `"google.com"` into your browser, the request that your browser makes to Google's server passes through the firewall on its way. 

- The firewall checks the incoming request to make sure it is allowed based on its security rules.

#### There are two main types of security rules that a firewall uses to check incoming requests:

1. Rules that allow or block traffic based on the source and destination of the request.

- For example, a firewall may be configured to block all traffic from certain countries or to allow only certain IP addresses to access the network.

2. Rules that allow or block traffic based on the type of traffic.

-  For example, a firewall may be configured to block all traffic on certain ports (such as those used by malware) or to allow only certain types of traffic (such as HTTP or HTTPS).

If the incoming request meets the security rules set by the firewall in front of Google's server, it is allowed through, and the browser is able to access the website.

- However, if the request does not meet the security rules, it is blocked, and the browser is unable to access the website.

### HTTPS/ SSL

HTTPS (Hypertext Transfer Protocol Secure) is a secure version of the HTTP protocol used to transmit data on the Internet. 

- It is used to encrypt the data transmitted between your browser and Google's server.

SSL (Secure Sockets Layer) and TLS (Transport Layer Security) are encryption protocols that are used to secure the data transmitted over HTTPS.

When the browser establishes a connection with Google's server using HTTPS, the browser and Google's server first agree on the version of SSL/TLS to use and then create a secure, encrypted channel for transmitting the data.

#### Here is an anology to explain what is happening:

- `HTTPS` is like a locked box that is used to send messages over the internet. When you want to send a message using `HTTPS`, you put the message in the locked box and send it to the person you want to receive the message. Only the person you are sending the message to has the `key` to unlock the box and read the message.

- `SSL/TLS` are like special codes that are used to lock and unlock the box. When you want to send a message using `HTTPS`, you and the person you are sending the message to agree on the code to use to lock and unlock the box. This way, only you and the person you are sending the message to know the code and can read the message.

- When you type `"google.com"` into your browser, the browser is like the person sending the message. The server that hosts `google.com` is like the person receiving the message. The browser sends a request for the webpage using `HTTPS`, which is like putting the request in a locked box and sending it to the server. The server then sends the webpage back to the browser using `HTTPS`, which is like putting the webpage in a locked box and sending it back to the browser.




