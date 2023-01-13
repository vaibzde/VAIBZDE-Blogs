# Day24 - An Introduction to HTTP: The Protocol of the Web

# Introduction

Welcome to the 24th blog in our 50-day blogging series, "Code Blog Repeat: A 50-Day Quest for Backend Mastery"! I am so glad you could join us on this journey to becoming a backend master.

In our previous blog, we discussed in detail about web servers and how they play a crucial role in handling requests and returning responses for the client. But have you ever wondered about the communication between the client and server? How does the client know what to ask for and how does the server know what to send back? This is where HTTP comes into play.

HTTP (Hypertext Transfer Protocol) is a set of rules that govern how information is transferred over the internet. It is not a language but a protocol that allows the client and server to communicate with each other by sending and receiving requests and responses. It is the backbone of the World Wide Web. In this blog, we will explore in detail what HTTP is, its importance on the internet and how it plays a crucial role in the communication between the client and server.

# What is HTTP?

HTTP, or Hypertext Transfer Protocol, is a protocol used for transmitting data over the internet. It is not a language, but a set of rules and guidelines that dictate how data should be structured and transmitted. These rules are followed by the client and the server to ensure that the communication between them is accurate and efficient.

HTTP is the foundation of the World Wide Web and is used for sending and receiving information between web clients and servers. When a client, such as a web browser, requests a web page from a server, the server sends the HTML, CSS, and JavaScript files that make up the page to the client. The client then renders the page for the user to view.

The HTTP protocol defines the structure and format of requests and responses, as well as the methods (such as GET, POST, PUT, and DELETE) that can be used to interact with resources on the web. It also provides a set of standard response codes that indicate the status of a request, such as 200 OK, 400 Bad Request, and 404 Not Found, which is used to communicate the success or failure of a request.

HTTP is a stateless protocol, which means that it does not maintain a connection between requests. Each request is treated as an independent transaction and does not rely on previous requests. This allows for scalability and flexibility, but it also means that additional mechanisms, such as cookies and sessions, are needed to maintain state.

HTTP plays a crucial role in the internet, allowing web clients and servers to communicate with each other efficiently and effectively. It allows us to access vast amounts of information easily and quickly, and it is the foundation of the World Wide Web.

# HTTP requests and HTTP response

HTTP can be divided into two main components: the request and the response.

The request is sent by the client to the server, and it contains the following information:

1. Method: The HTTP method (GET, POST, PUT, DELETE, etc.) used to interact with the resource.
    
2. URI (Uniform Resource Identifier): The address of the resource being requested.
    
3. HTTP Version: The version of the HTTP protocol used in the request.
    
4. Headers: Additional information about the request, such as the type of content being sent, the client's preferred languages, and authentication credentials.
    
5. Body: The content of the request, if any.
    

The response is sent by the server to the client, and it contains the following information:

1. HTTP Version: The version of the HTTP protocol used in the response.
    
2. Status Code: A three-digit number that indicates the status of the response, such as 200 OK, 404 Not Found, and 500 Internal Server Error.
    
3. Reason Phrase: A short description of the status code.
    
4. Headers: Additional information about the response, such as the type and size of the content, the server's preferred languages, and the location of the resource.
    
5. Body: The content of the response, if any.
    

It's worth noting that the headers and body are optional and may not be present in every request or response. The headers and body can contain additional information that can be used to specify additional information about the request or the response. HTML, CSS, and JavaScript files are typically included in the body of an HTTP response sent by a server to a client.

Here's an example of what a simple HTTP request and response might look like:

HTTP Request:

```js
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0
Accept: text/html
```

HTTP Response:

```js
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1234

<!DOCTYPE html>
<html>
<head>
<title>Example website</title>
</head>
<body>
<h1>Welcome to my website!</h1>
</body>
</html>
```

In the example above, the client (such as a web browser) is sending a GET request to the server, asking for the file "index.html" located on "[www.example.com](http://www.example.com)". The server then responds with an HTTP/1.1 200 OK status code, indicating that the request was successful. The response also includes headers that specify the content type as "text/html" and the content length as "1234" bytes. The message body of the response is the HTML code for the requested webpage.

## Types of HTTP requests

HTTP requests are the way in which clients communicate with servers. There are several types of HTTP requests, each with a specific purpose and usage. Here is a brief overview of the most commonly used HTTP request methods:

1. GET: The most commonly used HTTP request method, a GET request is used to retrieve information from the server. When a client makes a GET request, it is asking the server to send back the contents of a specified resource. GET requests do not have a request body and should not alter the state of the server.
    
2. POST: A POST request is used to submit new data to the server, typically to create a new resource. The request body in a POST request contains the data being sent to the server.
    
3. PUT: A PUT request is used to update an existing resource on the server. The request body in a PUT request contains the updated data.
    
4. DELETE: A DELETE request is used to delete a resource on the server. It does not have a request body.
    
5. HEAD: A HEAD request is similar to a GET request, but it only returns the headers of the response, not the body.
    
6. OPTIONS: An OPTIONS request is used to retrieve the supported HTTP methods of a resource.
    
7. PATCH: A PATCH request is used to partially update a resource. It is similar to a PUT request, but it only updates the specific fields specified in the request body.
    
8. CONNECT: A CONNECT request is used to establish a network connection to a resource.
    
9. TRACE: A TRACE request is used to retrieve a diagnostic trace of the request message.
    

Each of these methods have a specific purpose and use case, and they should be used appropriately when interacting with a server. It is important to note that not all methods are supported by all servers or resources.

## HTTP response codes

HTTP response codes are an important aspect of the HTTP protocol. They provide a way for servers to communicate the status of a request to clients. Understanding the different response codes and their meanings is essential for properly handling and debugging issues with web applications.

Response codes are three-digit numbers that are grouped into five classes: 1xx (Informational), 2xx (Successful), 3xx (Redirection), 4xx (Client Error) and 5xx (Server Error)

1. The 2xx class represents success status, the most common of which is 200 OK, indicating that the request was successfully received and processed by the server.
    
2. The 3xx class represents redirection status, the most common of which is 301 Moved Permanently, indicating that the requested resource has been permanently moved to a new location.
    
3. The 4xx class represents client error status, the most common of which is 404 Not Found, indicating that the requested resource could not be found on the server.
    
4. The 5xx class represents server error status, the most common of which is 500 Internal Server Error, indicating that an error occurred on the server while processing the request.
    

It's important to understand that these response codes are not only used for the website but also for all the APIs, to indicate the status of the request. For example, a 200 OK response code indicates that the request was successful and the requested resource was returned, while a 404 Not Found response code indicates that the requested resource could not be found.

The most common HTTP response codes are:

1. 200 OK: Indicates that the request was successful, and the server has returned the requested resource.
    
2. 201 Created: Indicates that a new resource was successfully created in response to the request.
    
3. 204 No Content: Indicates that the request was successful, but the server has not returned a response body.
    
4. 400 Bad Request: Indicates that the request was malformed or invalid.
    
5. 401 Unauthorized: Indicates that the request requires authentication and the client did not provide valid credentials.
    
6. 403 Forbidden: Indicates that the client does not have permission to access the requested resource.
    
7. 404 Not Found: Indicates that the requested resource could not be found on the server.
    
8. 500 Internal Server Error: Indicates that an error occurred on the server while processing the request.
    

By understanding the different response codes and their meanings, developers can better handle and debug issues with their web applications. It's also important to note that different APIs may use different response codes and it's a good idea to check the documentation of the API to understand the different status codes.

## GET vs POST method

The GET and POST methods are the two most commonly used HTTP methods for making requests to a server. Both methods are used to retrieve or send data to a server, but they have distinct differences in their functionality and usage.

The GET method is used to retrieve information from the server, while the POST method is used to submit new data to the server. GET requests are cached by the browser, allowing for faster loading times for repeat requests. However, this can also lead to stale data being displayed if the resource has been modified on the server. On the other hand, POST requests are not cached by the browser, ensuring that the most up-to-date data is always retrieved from the server.

Bookmarking is a feature that allows a user to save the URL of a webpage for future reference. GET requests are bookmarkable, meaning that the URL and any data associated with it can be saved. However, POST requests are not bookmarkable, as the data is sent in the request body and not in the URL.

Caching is the process of storing a copy of a resource on the client-side to improve performance. GET requests can be cached by both the browser and server, while POST requests are not cached. This can make GET requests faster, but can also lead to stale data being displayed.

In terms of security, GET requests are generally considered less secure than POST requests. This is because the data sent in a GET request is included in the URL and can be easily intercepted by malicious actors. POST requests, on the other hand, send data in the request body, making it more difficult for unauthorized parties to access it.

Lastly, GET requests are limited in size, usually around 2 KB, while POST requests have no such limit. This means that POST requests are generally better suited for sending larger amounts of data.

# HTTPS

HTTPS stands for Hypertext Transfer Protocol Secure. It is a secure version of the standard HTTP protocol used to transfer data over the internet. HTTPS encrypts the communication between the client and the server, making it more secure and private.

The main difference between HTTP and HTTPS is that HTTPS uses a secure SSL/TLS certificate to encrypt the data being transmitted. This encryption is accomplished through the use of a public and private key pair. The public key encrypts the data, and the private key decrypts it. This ensures that only the intended recipient can read the data being sent.

Encryption is important because it helps protect sensitive information, such as passwords and personal data, from being intercepted by malicious actors. It also helps to prevent man-in-the-middle attacks, where a third party intercepts and alters the data being transmitted.

To check if a website is secure with HTTPS, look for the lock icon in the browser address bar. If the icon is present and the website's URL begins with "https", the website is using HTTPS. Additionally, you can check the SSL/TLS certificate by clicking on the lock icon, which will display information about the certificate and its authenticity.

HTTPS is a more secure version of the standard HTTP protocol and is crucial for protecting sensitive information and ensuring the privacy of data being transmitted on the internet. It is important for website owners to implement HTTPS in order to protect their users' data and for users to check for the presence of HTTPS on websites before entering any sensitive information.

# Conclusion

In conclusion, in this blog we have explored the importance and inner workings of HTTP, the backbone of the World Wide Web. We have delved into the components of HTTP requests and responses, the different types of HTTP methods, and the significance of HTTP response codes. We have also discussed the difference between HTTP and HTTPS and the importance of encryption in maintaining a secure connection. I hope that this blog has provided a deeper understanding of the role that HTTP plays in the communication between the client and server.

I thank you for taking the time to read this blog as part of our 50 day blogging series "Code Blog Repeat: A 50 Day Quest for Backend Mastery". I hope that you have found this blog informative and insightful. I would love to hear your feedback and thoughts on the series, so please feel free to leave a comment or share the post with others. Keep following the series as we continue our quest for backend mastery.