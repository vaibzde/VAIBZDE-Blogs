# #Day27 - Routing in ExpressJS

Welcome to Day 27 of our 50-day quest for back-end mastery! In our previous blog post, we introduced Express and discussed why it is needed for back-end development. Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

Today, we will be diving deeper into Express and discussing routing.

Routing in Express allows us to handle different HTTP requests and map them to different actions or controllers in our application. This is essential for building a scalable and maintainable web application. Routing in Express is simple and easy to use, making it a popular choice among developers.

%[https://twitter.com/vaibzde/status/1615038781916344320?s=20&t=T5b9Nv-M0id759pzkuIqsw] 

By the end of this blog post, you will have a solid understanding of how to use routing in your Express applications.

Let's Go!!

# What is routing in Express and why it is important

Routing in Express refers to the process of determining how an application should respond to a client request to a particular endpoint, which is defined by a URI (Uniform Resource Identifier) and a specific HTTP request method (GET, POST, PUT, DELETE, etc.). In other words, routing is the process of determining what code should run when a user visits a specific URL or makes a specific type of request.

Routing is important in Express because it allows developers to handle different types of requests in different ways. For example, a GET request to the homepage of a website should return a different response than a POST request to the contact form. Without routing, all requests would be handled in the same way, which would make the application inflexible and difficult to maintain.

Routing in Express is also important because it helps to keep the codebase organized. By separating the logic for handling different types of requests, it becomes easier to read, understand and modify the code. Additionally, routing allows for the creation of reusable controllers, which can handle similar types of requests in different parts of the application.

Simply put, routing in Express is the process of determining how an application should respond to a client request. It allows developers to handle different types of requests in different ways, and helps to keep the codebase organized. This makes it essential for building scalable and maintainable web applications.

# Setting up routing in an Express application

Setting up routing in an Express application is a straightforward process. In this section, we will go over the steps to get started with routing in your Express application.

Step 1: Import and create an Express application instance To use routing in Express, you will first need to import the Express module and create an Express application instance. You can do this by adding the following lines of code at the top of your server file:

```js
const express = require('express');
const app = express();
```

Step 2: Define routes To define a route in Express, you will use the app.method() function, where method is the HTTP request method (e.g. GET, POST, PUT, DELETE) and the first argument is the URL endpoint. For example, the following code defines a route for the homepage of a website:

```js
app.get('/', (req, res) => {
  res.send('Welcome to the homepage');
});
```

Step 3: Start the Express server Finally, you will need to start the Express server. This can be done by calling the listen() function on your Express application instance, passing in the port number you want to use. For example:

```js
app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

That's it! You have now set up routing in your Express application. You can now start defining additional routes and handling different types of requests in different ways. Keep in mind that you can also use routing modules and Router() class to set up routing in express.

It is important to note that the order of the routes is important. Express will match the route that comes first in the file, so make sure to put the most specific routes first and the catch-all routes last.

# Creating different types of routes (e.g. GET, POST, PUT, DELETE)

Creating different types of routes in Express is easy and straightforward. In this section, we will go over how to create routes for the most commonly used HTTP request methods: GET, POST, PUT, and DELETE.

Here is an example of how you can define routes for these different methods:

```js
app.get('/', (req, res) => {
  res.send('Welcome to the homepage');
});

app.post('/submit', (req, res) => {
  res.send('Form submitted successfully');
});

app.put('/update/:id', (req, res) => {
  res.send(`Updating item with ID: ${req.params.id}`);
});

app.delete('/delete/:id', (req, res) => {
  res.send(`Deleting item with ID: ${req.params.id}`);
});
```

In this example,

* The first route is a GET request to the homepage. When a user visits this route, the server will respond with the message "Welcome to the homepage".
    
* The second route is a POST request to the "/submit" endpoint. When a user submits a form to this route, the server will respond with the message "Form submitted successfully".
    
* The third route is a PUT request to the "/update/:id" endpoint. This route accepts a route parameter, ":id", which is used to update an item with a specific ID.
    
* The final route is a DELETE request to the "/delete/:id" endpoint. This route also accepts a route parameter, ":id", which is used to delete an item with a specific ID.
    

Routing in Express is done by matching the method and path of the request to a corresponding route. If a match is found, the associated callback function is executed. Additionally, Express allows for the use of a Router() instance to create modular, mountable route handlers, making it easier to organize and reuse routes within an application..

A mountable route handler is a way to organize and reuse the same route handlers across different parts of your application. It allows you to mount a router on a specific path on the main app instance, so that all routes defined on the router will be prefixed with that path.

By understanding the different types of routes, you can create a flexible and scalable web application that can handle different types of requests in different ways.

# Using routing parameters

Using routing parameters in Express allows you to capture values from the client and use them in your route handlers. These parameters are placeholders in the URL that can be used to retrieve dynamic data from the client.

For example, you can use routing parameters to retrieve the ID of a specific product from the client and use it to display the details of that product. The following code defines a route for displaying a specific product, where `:id` is a routing parameter:

```js
app.get('/product/:id', (req, res) => {
  res.send(`Displaying product with ID: ${req.params.id}`);
});
```

In this example, when a client makes a GET request to the endpoint "/product/123", the server will respond with the message "Displaying product with ID: 123". The [`req.params.id`](http://req.params.id) is used to retrieve the value of the `:id` routing parameter.

You can also use multiple routing parameters in a single route. For example, you can use routing parameters to retrieve the ID and name of a specific product and use them to display the details of that product.

```js
app.get('/product/:id/:name', (req, res) => {
  res.send(`Displaying product with ID: ${req.params.id} and Name: ${req.params.name}`);
});
```

Using routing parameters is a powerful feature of Express that allows you to create dynamic and flexible web applications. It allows you to capture values from the client and use them in your route handlers, making it easy to retrieve dynamic data from the client.

# Best practices for routing in Express include:

* Ordering routes correctly: Express will match the route that comes first in the file, so make sure to put the most specific routes first and the catch-all routes last.
    
* Using Router() instances: Use Router() instances to create modular, mountable route handlers, this makes it easy to organize your routes and reuse them across different parts of your application.
    
* Keeping routes simple: Try to keep routes simple and avoid using too many middleware functions. This makes it easier to understand and maintain your code.
    
* Using route parameters correctly: Use routing parameters to capture values from the client and use them in your route handlers. Remember that routing parameters are optional, if the client does not provide a value for the routing parameter, the value will be undefined.
    
* Validating requests: Use middleware functions to validate requests and handle errors. This helps to prevent malicious or incorrect requests from reaching your route handlers.
    
* Documenting routes: Document your routes, including the route path, the HTTP method, and the expected request and response formats. This makes it easier for other developers to understand and work with your code.
    

By following these best practices, you can create a well-structured, maintainable, and scalable Express application that can handle different types of requests in different ways.

# Conclusion

In conclusion, we covered routing in Express in this blog post. We discussed the importance of routing in building scalable and maintainable web applications, and how it allows developers to handle different types of requests in different ways. We also went over the steps to set up routing in an Express application and how to define different types of routes like GET, POST, PUT, DELETE. We also discussed about routing parameters, which are placeholders in the URL that can be used to retrieve dynamic data from the client and best practices for routing in Express.

%[https://twitter.com/vaibzde/status/1615039068152422405?s=20&t=T5b9Nv-M0id759pzkuIqsw] 

I hope that you found this blog post informative and helpful in understanding routing in Express. Thanks for reading and I would love to hear your thoughts and experiences in the comments section. Don't forget to share the blog with your friends and colleagues.