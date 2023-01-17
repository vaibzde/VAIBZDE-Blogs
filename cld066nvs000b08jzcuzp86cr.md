# #Day28 - Middleware in Express

Welcome to Day 28 of our blogging series "Code, Blog, Repeat: A 50-Day Quest for Back-End Mastery"! Yesterday, we covered routing in Express, and today we're going to dive into the world of middlewares.

Think of middlewares as the secret agents of Express - they work behind the scenes to make sure everything runs smoothly. But don't let their covert nature fool you - they're an essential part of any Express application.

%[https://twitter.com/vaibzde/status/1615312944128217088?s=20&t=uKpkUjtz6K9IKrSMg1B4HA] 

In this blog post, we're going to discuss what middlewares are, how to use built-in middlewares, how to create custom middlewares, and how to implement middlewares in the simple Express server we built on Day 27. So sit back, relax, and get ready to learn about the unsung heroes of Express. Let's get started!

## Introduction to middlewares in Express:

Have you ever wondered what happens behind the scenes when you make a request to an Express server? Well, that's where middlewares come in. In the context of Express, middlewares are functions that are executed before the final route handler. They're like little helpers that can do things like parsing incoming data, adding headers to a response, or even authenticating a user.

To give you an idea of how middlewares fit into the request-response cycle, let's imagine a scenario where a client makes a request to an Express server. As soon as the request hits the server, it gets passed through a series of middlewares before it reaches its final destination - the route handler. Each middleware has the opportunity to inspect the request, make changes to it, and even halt the request if needed. Once all the middlewares have done their job, the request is passed on to the final route handler, which is responsible for generating a response. This response is then passed through another series of middlewares, which can make further changes before it's sent back to the client.

Now, you might be wondering why we would want to use middlewares. The answer is simple - they help us separate concerns in our code. For example, instead of adding authentication logic in every route handler, we can simply use an authentication middleware that runs before every route. This not only makes our code more organized, but it also makes it easier to maintain. Additionally, middlewares can be reused across different routes and even across different projects, making them a powerful tool in our Express toolbox.

In summary, middlewares are functions that are executed before the final route handler and help us separate concerns in our code. They give us the opportunity to inspect the request and make changes to it, and can be reused across different routes and projects.

## Using built-in middlewares:

Now that we understand what middlewares are and why they're useful, let's take a look at some of the most commonly used built-in middlewares in Express.

These are pre-made helpers that can be easily added to our Express app to do specific tasks.

One example of a built-in middleware is called "body-parser". It helps us read the information that the client sends to the server in the request body. For example, if a client sends a message in a `POST` request, body-parser will help us read that message and make it available for us to use.

Another built-in middleware is called "cors". It helps us handle requests from different websites (or "origins"). It makes sure that only certain websites are allowed to make requests to our server.

Finally, "helmet" is another middleware that helps us add some security to our Express app by setting some security headers.

Using built-in middlewares is very easy, you just need to import them in your application and then use the `app.use()` method to add them to your app. For example:

```js
const express = require('express');
const bodyParser = require('body-parser');
const cors = require('cors');
const helmet = require('helmet');

const app = express();

app.use(bodyParser.json());
app.use(cors());
app.use(helmet());
```

* `app.use(bodyParser.json());`: This line is telling the application to use the `body-parser` middleware. The `json()` method is used to parse incoming request bodies in JSON format. This means that if a client makes a `POST` request with a JSON payload, the `body-parser` middleware will parse that payload and make it available in the request object as `req.body`. This makes it easy for us to access data sent in the request body.
    
* `app.use(cors());`: This line is telling the application to use the `cors` middleware. `cors()` is a middleware that allows us to easily set up Cross-Origin Resource Sharing (CORS) on our Express server. CORS is a security feature that prevents a web page from making requests to a different domain than the one it came from. By using `cors()`, we can specify which domains are allowed to make requests to our server.
    
* `app.use(helmet());`: This line is telling the application to use the `helmet` middleware. `helmet` is a middleware that helps to secure our Express app by setting various HTTP headers. It sets headers like X-Content-Type-Options, X-Frame-Options and more.
    

Express application uses the `app.use()` method to add these middlewares to the application. This will configure these middlewares for our entire application, so that every incoming request will pass through them. This makes our application more efficient and secure.

By doing this, these middlewares will be used for every incoming request and will help us handle common tasks in our Express app.

## Creating custom middlewares:

So far, we've talked about using built-in middlewares in Express, but what if none of the built-in middlewares fit your needs? That's where custom middlewares come in. Custom middlewares are functions that you can create yourself to handle specific tasks in your Express application.

Creating a custom middleware is quite simple, all you need to do is create a function that takes three arguments `req`, `res`, and `next`. The `req` and `res` objects are the same objects that are passed to route handlers, and the `next` argument is a function that tells Express to move on to the next middleware or route handler in the stack. The custom middleware function can then perform any logic it needs to before calling the `next` function.

The `next` argument in a custom middleware function is a function that tells Express to move on to the next middleware or route handler in the stack. It's important to understand that in Express, middlewares and route handlers are executed in a specific order, and the `next` function is used to control this flow.

Here's an example of a custom middleware function that checks if a user is authenticated:

```js
function isAuthenticated(req, res, next) {
    if (req.user) {
        next();
    } else {
        res.status(401).send('Unauthorized');
    }
}
```

In this example, the custom middleware function checks if the `req.user` object exists. If it does, that means the user is authenticated, and the `next()` function is called, allowing the request to continue to the next middleware or route handler. If the `req.user` object does not exist, that means the user is not authenticated, and the middleware sends a `401 Unauthorized` response to the client.

Another example of a custom middleware function is for logging the request:

```js
function logRequest(req, res, next) {
    console.log(`${req.method} request made to ${req.url} at ${new Date()}`); 
    next(); }
```

In this example, the custom middleware function simply logs the request method, the requested URL, and the date and time of the request to the console. Then it calls the `next()` function to continue the request-response cycle.

You can use the custom middleware by using the `app.use()` method just like the built-in middlewares.

```js
app.use(isAuthenticated); 
app.use(logRequest);
```

The main difference between using custom middlewares and using built-in middlewares is that custom middlewares are specific to your application, whereas built-in middlewares are general purpose and can be used in any application. Using custom middlewares allows you to have more control over the flow of your application and handle specific tasks. However, using built-in middlewares can save you time and make your code more organized.

In short, custom middlewares are functions that you can create yourself to handle specific tasks in your Express application. They are created by creating a function that takes three arguments `req`, `res`, and `next`. Custom middlewares can be added to your application using the `app.use()` method, just like built-in middlewares. Using custom middlewares allows you to have more control over the flow of your application and handle specific tasks, while using built-in middlewares can save you time and make your code more organized.

## Implementing middleware in the simple express server built in Day 27

Sure, here is an example of how to implement middleware in the simple express server built in Day 27:

```js
const express = require('express');
const app = express();

// Middleware function 1
const logMiddleware = (req, res, next) => {
  console.log(`Received ${req.method} request at ${req.url}`);
  next();
};

// Middleware function 2
const authMiddleware = (req, res, next) => {
  // check for authentication
  if(!req.headers.authentication) {
    return res.status(401).send('Unauthorized');
  }
  next();
};

// Apply middleware to specific routes
app.get('/', logMiddleware, (req, res) => {
  res.send('Welcome to the homepage');
});

app.post('/submit', authMiddleware, (req, res) => {
  res.send('Form submitted successfully');
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

In this example, we have defined two middleware functions, `logMiddleware` and `authMiddleware`. The `logMiddleware` function logs the request method and URL to the console, while the `authMiddleware` function checks for the presence of an `authentication` header in the request and returns a 401 status if it is not present.

We have then applied these middleware functions to specific routes using the `app.get()` and [`app.post`](http://app.post)`()` methods. The `logMiddleware` function is applied to the homepage route, while the `authMiddleware` function is applied to the submit route.

When a request is made to the server, it goes through the middleware functions before reaching the route's callback function. In this example, a GET request to the homepage will first pass through the `logMiddleware` function, which will log the request method and URL, before reaching the route's callback function and returning a response to the client. A POST request to the '/submit' endpoint will pass through the `authMiddleware` function first, which will check for the presence of the `authentication` header, before reaching the route's callback function and returning a response to the client.

It's important to note that the order of the middleware functions passed to the route's callback function matters. In this example, the `logMiddleware` function is applied before the `authMiddleware` function for the homepage route, and the order is reversed for the submit route.

Additionally, you may also apply middleware to all routes by using the `app.use()` method or to a group of routes by using the `Router()` instance.

When working with middlewares, it's important to keep an eye out for common issues such as headers or body not being parsed, or middlewares not being called in the expected order. To debug these issues, you can use tools such as Postman to check the headers and body of the requests, or use the `console.log()` statements to check the flow of the request-response cycle.

So we get that, middleware functions in express allows you to perform specific actions on requests before they reach the route's callback function, and also allows you to handle errors or authentication, making your application more robust and secure.

# Conclusion:

In this blog post, we've discussed middlewares in Express and how they fit into the request-response cycle. We've covered the benefits of using middlewares, including built-in middlewares such as body-parser, cors and helmet, and how to use them in an Express application. We've also discussed the process of creating custom middlewares and provided examples of custom middlewares that can be used to handle common tasks such as authentication and logging. We've also explained the difference between using custom middlewares and using built-in middlewares.

To sum up, middlewares in Express are powerful tools that can help you handle common tasks in your application and make your code more organized and efficient. Whether you're using built-in middlewares or creating custom middlewares, they can save you time and improve the performance of your application.

If you're interested in learning more about middlewares in Express, here are some additional resources:

* The official Express.js documentation on middlewares: [https://expressjs.com/en/guide/using-middleware.html](https://expressjs.com/en/guide/using-middleware.html)
    

Thank you for reading this blog post and for your interest in learning about middlewares in Express. I hope you found it informative and helpful. I encourage you to share your knowledge and experiences with Express and middlewares, and let me know if you have any suggestions or questions. Thanks for reading and I look forward to your feedback.

> Happy Programming!