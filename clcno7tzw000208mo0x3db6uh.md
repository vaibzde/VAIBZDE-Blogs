# #Day19 - Intro to Asynchronous Programming in JavaScript

# Introduction

Hello and welcome to the 19th day of our blogging series on the back end mastery!

Today, we will be diving into the world of asynchronous programming. If you recall from our previous blog post on Day 16, we briefly touched on the topic of synchronous programming and how the event loop in Node.js enables it to achieve asynchronous behaviour.

In this blog, we will be revisiting the concepts of synchronous and asynchronous programming, and exploring in more detail ways to achieve asynchronous behaviour.

So grab a cup of coffee and join us on this exciting journey to learn more about asynchronous programming!

Before discussing asynchronous programming, it is important to first understand what synchronous programming is.

# Synchronous programming

Synchronous programming refers to the sequential execution of program code, meaning that the code is written in a top-down fashion and each line is executed one at a time, in the order that it appears. For example, in JavaScript, the code will wait for each line to be completely executed before moving on to the next line.

To understand synchronous programming, consider a group of customers entering a restaurant and being seated at different tables. In a synchronous scenario, each customer would have to wait for their food to be prepared before the waiter can take the next customer's order. This is similar to how synchronous programming works

Cons of Synchronous Programming

* The next line of code will not be executed until the previous line has been completed, which can lead to delays if a line takes a long time to retrieve and process data.
    
* Not suitable for real-time applications where it is not feasible to wait for certain processes to complete before moving on to the next task.
    
* Can lead to blocks or freezes in the program if a line takes an unexpectedly long time to complete.
    

Now, let's discuss asynchronous programming.

# Asynchronous programming

Asynchronous programming refers to the execution of code functions without waiting for other code functions to execute. This means that multiple lines of code can be executed concurrently, rather than one line at a time in a sequential manner. Asynchronous code is often used in programming contexts where it is not feasible to wait for certain processes to complete before moving on to the next task.

For example, in JavaScript, asynchronous code is often used when working with external resources such as databases or APIs. This is because these types of operations can take a long time to complete, and using asynchronous code allows the program to continue executing other lines of code while the operation is being performed in the background. This can lead to more efficient programs and a better user experience.

Using the restaurant example again, in an asynchronous scenario, for the group of customers entering a restaurant, the waiter would be able to take the orders of multiple customers at the same time, rather than waiting for each customer's food to be prepared before moving on to the next customer. The kitchen staff would then prepare the food for all of the customers simultaneously, rather than completing one customer's food before starting on the next customer's order. This is similar to how asynchronous programming works in a programming context.

## Use Cases for Asynchronous Programming

* When making requests to external APIs, such as retrieving data from a weather service or checking the status of a flight, it can take a while for the server to respond. Using asynchronous code allows the program to continue executing other lines of code while waiting for the API response, rather than being "stuck" until the response is received.
    
* If a web page contains large resources such as images or videos, asynchronous code can be used to load these resources without blocking the rest of the program. This can improve the user experience by allowing the page to remain responsive while the resources are being loaded.
    
* Queries to a database can take a long time to complete, especially for large datasets. By using asynchronous code, the program can continue executing other lines of code while waiting for the database operation to complete, rather than being stuck in a "holding pattern."
    
* Asynchronous code is often used in real-time applications such as chat apps or online games, as it allows the program to handle multiple requests or events concurrently. This can lead to a more seamless and interactive user experience.
    
* If a task is expected to take a long time to complete, such as generating a report or performing a complex calculation, asynchronous code can be used to allow the program to continue executing other lines of code while the task is being performed. This can improve the overall efficiency of the program and prevent it from "freezing" while the task is being completed.
    

# Different Ways to Achieve Asynchronous Execution in JavaScript

JavaScript provides several different ways to achieve asynchronous execution, each with its own benefits and drawbacks. Here are a few of the most common techniques:

* **Callbacks**: Callbacks are functions that are passed as arguments to other functions and are executed at a later time. They are often used inside Browser API/Web API functions or events, such as `setTimeout` or event handlers like `click`, `mouseover`, `scroll`, etc. Callbacks can be a simple way to achieve asynchronous execution, but they can also lead to code that is difficult to read and maintain.
    
* **Promises**: Promises are objects that represent the result of an asynchronous operation. They provide a way to handle asynchronous results in a more structured and composable way than using callbacks. Promises can be chained together and allow for more flexibility and error handling than callbacks.
    
* **Async/Await**: The `async` and `await` keywords provide a more intuitive and easy-to-use syntax for writing asynchronous code in JavaScript. They allow you to write asynchronous code that looks and behaves like synchronous code, making it easier to read and understand. In addition, `async/await` is generally considered a better alternative to promises in many cases, as it provides a more familiar syntax and allows for better error handling. While it does require the use of `async` functions and is not supported in all environments, `async/await` can be a powerful tool for improving the readability and maintainability of your code.
    

In our upcoming blogs, we will explore deeper into each of these methods for achieving asynchronous execution in JavaScript: callbacks, promises, and async/await. Stay tuned!

# Conclusion

In this blog, we have explored the concepts of synchronous and asynchronous programming in JavaScript and the different ways to achieve asynchronous behaviour. We have learned that asynchronous programming allows for the concurrent execution of multiple lines of code, while synchronous programming executes code sequentially. We have also discussed the benefits and drawbacks of each approach, and the different use cases for asynchronous programming. In future blog posts, we will delve deeper into each of the methods for achieving asynchronous execution in JavaScript: callbacks, promises, and async/await. Stay tuned!

> Thankyou for reading the blog :)