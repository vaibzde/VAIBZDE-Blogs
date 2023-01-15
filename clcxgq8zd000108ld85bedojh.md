# #Day26 - Introduction to Express JS

Welcome to the 26th day of our blog series "Code Blog Repeat: A 50-day quest for backend mastery." Today, we will be covering the basics of Express, a popular web framework for Node.js

## What is Express and Why is it Needed

Express is a minimal, flexible, and open-source framework built on top of Node.js. It is used for creating web applications and APIs.

When building a web application or API, there are several common tasks that need to be performed such as handling HTTP requests and responses, routing, parsing requests, and handling errors. Express provides a simple and easy-to-use API that abstracts away many of the low-level details and makes it easy to handle all of these tasks.

A framework, in general, is a collection of pre-written code that provides a structure for building a software application. Express is a web application framework for Node.js that provides a set of features for web and mobile applications.

Express solves the problem of handling the low-level details of HTTP requests and responses when building a web application or API using Node.js. It provides a simple and flexible way to handle routing, middleware, and other functionality needed for a web server. It is minimal, meaning it doesn't include extra functionality that is not needed, and it is flexible, meaning it can be used for a wide variety of web applications and APIs.

### What is an API and How Express Provides its Own Set of APIs

An API, or Application Programming Interface, is a set of rules and protocols for building and interacting with software applications. It allows different pieces of software to communicate and share data in a consistent and predictable manner. In the context of web development, an API is a set of endpoints that allows a client (such as a web browser or mobile app) to interact with a server and retrieve or manipulate data.

Express, as a web framework for Node.js, provides its own set of APIs that developers can use to easily handle common tasks when building web applications and APIs. These APIs abstract away the low-level details and provide a consistent and predictable way to handle tasks such as routing, parsing requests, and handling errors. Developers can focus on building their application's logic and functionality instead of worrying about the low-level details of handling HTTP requests and responses. In this way, it makes it easy for developers to create their own APIs and applications and handle the requests in a consistent and predictable manner

## Setting up an Express Application

Setting up an Express application is a simple process that involves importing the Express package, creating an instance of the Express application, and configuring it to handle different routes and functionality.

To start, you need to have Node.js and npm (Node Package Manager) installed on your machine. You can download and install Node.js from the official website. Once Node.js and npm are installed, you can use npm to install the Express package by running the following command in the terminal:

```js
npm install express
```

Once the Express package is installed, you can import it in your JavaScript file and create an instance of the Express application. The following code snippet shows an example of how to import the Express package and create an Express application:

```js
const express = require('express');
const app = express();
```

Once you have created an Express application, you can configure it to handle different routes and functionality. You can do this by using the various methods provided by the Express application, such as `app.get()`, `app.post()`, `app.put()`, `app.delete()` for handling different types of HTTP requests, and `app.use()` for using middleware.

It's important to note that once you have set up the Express application, you can use it to handle HTTP requests and responses, routing, parsing requests, and handling errors. And with the help of this application, you can create a web server that listens to a specific port on your machine and handle the HTTP requests.

## Comparison of creating an HTTP server with and without Express

When building a web application or an API, one of the main tasks is to handle HTTP requests and responses. Without a framework such as Express, creating an HTTP server in Node.js would require a lot of code and manual handling of various tasks such as routing, parsing requests, and handling errors. Express, on the other hand, provides a simple and clean API that makes it easy to handle all of these tasks.

Let's take a look at an example of creating a simple HTTP server with and without Express.

Without Express:

```js
const http = require('http');
const server = http.createServer((req, res) => {
  // handle request and response
});
server.listen(3000);
```

With Express:

```js
const express = require('express');
const app = express();
app.listen(3000);
```

As you can see, Express significantly simplifies the process of creating an HTTP server by abstracting away many of the low-level details and providing a simple and easy-to-use API.

The `app.listen()` method is a method provided by the Express application that allows you to configure the application to listen to a specific port on your machine

Express provides many features such as routing, middleware, and error handling, that are essential for creating a web application or an API. By using Express, you can handle the low-level details of handling HTTP requests and responses in a much more manageable way.

In summary, Express simplifies the process of creating an HTTP server by abstracting away many of the low-level details and providing a simple and easy-to-use API. With Express, you can handle routing, middleware, and other functionality needed for a web server in a much more manageable way. I hope this section has provided you with a better understanding of how Express simplifies the process of creating an HTTP server.

## Conclusion

In conclusion, Express is a minimal and flexible web framework for Node.js that makes it easy to handle common tasks such as handling HTTP requests and responses, routing, parsing requests, and handling errors. It provides a simple and easy-to-use API that abstracts away many of the low-level details and makes it easy to handle all of these tasks.

Express is solving the problem of making it easy to handle the low-level details of handling HTTP requests and responses when building a web application or API using Node.js. It provides a simple and flexible way to handle routing, middleware, and other functionality needed for a web server. It is minimal, meaning it doesn't include a lot of extra functionality that is not needed, and it is flexible, meaning it can be used for a wide variety of web applications and APIs.

We have also seen how setting up an Express application is a simple process that involves importing the Express package, creating an instance of the Express application, and configuring it to handle different routes and functionality. And we have also seen the difference of creating an HTTP server with and without Express.

We hope you have gained a better understanding of Express and its capabilities. As always, we encourage you to share your thoughts and experiences in the comments section below. Thank you for reading!