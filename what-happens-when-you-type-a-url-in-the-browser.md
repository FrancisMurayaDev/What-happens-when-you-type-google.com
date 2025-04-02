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




