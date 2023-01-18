# #Day29 - Templating and Rendering in Express

Welcome to Day 29 of our blogging series "Code, Blog, Repeat: A 50-Day Quest for Back-End Mastery"! Yesterday, we covered middlewares in Express, and today we're going to explore the world of templating and rendering.

As we built our simple express server on Day 27, now it's time to make it more interactive by adding views and templates. Templating and rendering in Express allows us to create dynamic web pages that can change based on the data we pass to them. In this blog post, we will discuss how to set up a template engine, render views and pass data to them, and create a simple view for the simple express server we built on Day 27.

Let's dive in and see how we can make our express server more interactive and user-friendly!

# Introduction:

When building web applications, one of the most important aspects is the user interface. This is where templating and rendering come into play. In the context of Express, templating refers to the process of creating reusable templates that can be used to generate dynamic web pages. A template is a basic layout of a web page, which includes placeholders for dynamic content. On the other hand, rendering refers to the process of taking a template and filling it with data to create a final web page that is sent to the client.

Using a template engine in Express can greatly improve the development process. With a template engine, you can separate the presentation logic from the application logic. This makes it easier to maintain and update the codebase. Additionally, using a template engine allows for a clear separation of concerns and makes it easier to create reusable and maintainable code.

Another benefit of using a template engine is that it allows you to use the same template for multiple pages, reducing the amount of code you need to write. This makes it easier to make changes to the user interface, and it also makes it easier to create a consistent user experience across your application.

Simply put, Templating refers to the process of creating a template, or a layout, that can be reused across multiple pages. This template typically includes the common elements of a webpage such as a header, footer, and navigation menu.

Rendering, on the other hand, refers to the process of filling in the data in the template to create the final HTML page that will be sent to the browser. This data can come from a variety of sources such as a database or an API.

For example, let's say we have an e-commerce website and we want to display a list of products on the homepage. Instead of hardcoding the HTML for each product, we can use a template engine to create a template that includes a loop to display all the products. Then, we can use the data from our database to fill in the template and create the final HTML page that will be sent to the browser..

# Setting up a template engine:

When it comes to templating in Express, there are several popular options to choose from. Two of the most popular choices are EJS and Handlebars. Both of these template engines are easy to use, have a large community of developers, and have plenty of resources available online.

### EJS

EJS (Embedded JavaScript) is a simple templating language that allows you to embed JavaScript code in your HTML. To set up EJS, you will first need to install it using npm by running `npm install ejs`. Once it is installed, you can set it as your template engine by adding the following code to your Express application:

```js
app.set('view engine', 'ejs');
app.set('views', path.join(__dirname, 'views'));
```

The first line sets the view engine to EJS, and the second line sets the location of your views. You will also need to create a views folder at the root of your application, and save your EJS templates in that folder.

### Handlebars

Handlebars is a popular templating language that is similar to EJS, but with a few extra features such as helpers and partials. To set up Handlebars, you will first need to install it using npm by running `npm install express-handlebars`. Once it is installed, you can set it as your template engine by adding the following code to your Express application:

```js
const exphbs  = require('express-handlebars');
app.engine('handlebars', exphbs({defaultLayout: 'main'}));
app.set('view engine', 'handlebars');
```

The first line imports the express-handlebars module, the second line sets the view engine to handlebars, and the third line sets the location of your views. You will also need to create a views folder in the root of your application, and save your Handlebars templates in that folder.

Both EJS and Handlebars are powerful and widely used template engines, and you can choose the one that best fits your needs. The above steps are the basic setup process to use these template engines, but you may find more detailed information in the documentation of these engines.

Setting up a template engine in an Express application is easy, you just need to choose a template engine and install it via npm, then set it as the view engine in your Express application, and create a views folder to store your templates.

# Creating a simple view for the simple express server:

As we have set up our template engine and understand the importance of templating and rendering in Express, let's now create a simple view for the simple express server we built on Day 27.

To start, let's create a new folder in our project called "views". Inside this folder, we will create a new file called "index.ejs" (assuming we are using EJS as our template engine). This file will be our view and will contain all the HTML markup for our page.

Next, we need to configure our express server to use this view. We can do this by using the `app.set()` method. In our server file, we can add the following code:

```js
app.set('view engine', 'ejs');
app.set('views', path.join(__dirname, 'views'));
```

This tells our express server to use EJS as the view engine and to look for views in the "views" folder.

Now, we can create a route in our server that renders the "index.ejs" view. We can use the `app.render()` method to do this. In our server file, we can add the following code:

```js
app.get('/', (req, res) => {
    res.render('index');
});
```

This tells our server to render the "index" view (which corresponds to the "index.ejs" file) when a client makes a GET request to the root route.

To pass data to our view, we can include an object as the second argument in the `res.render()` method. For example, if we wanted to pass a message to our view, we can do the following:

```js
app.get('/', (req, res) => {
    res.render('index', { message: 'Hello World!' });
});
```

In our "index.ejs" file, we can then access this message using EJS syntax `(`&lt;%= message %&gt;`)`

It is important to notice that Templating and Rendering in Express is implemented at the time of rendering the views to the client. It makes the development process easier and more efficient. It also makes the separation of concerns clear by keeping the logic of your template engine by adding the following code to your Express application:

```js
const express = require('express'); 
const exphbs = require('express-handlebars'); 
const path = require('path');

const app = express();

app.engine('handlebars', exphbs({ 
defaultLayout: 'main', 
layoutsDir: path.join(__dirname, 'views/layouts') })); 
app.set('view engine', 'handlebars'); 
app.set('views', path.join(__dirname, 'views'));
```

The first line requires the express-handlebars module, and the second line sets the view engine to handlebars. The third line sets the location of your views, and the fourth line sets the default layout to use.

Creating a simple view for the simple express server:

Now that we have our template engine set up, we can start creating views for our server. Let's create a simple view that will display a greeting message to the user. We will use the template engine we set up above to create the view.

Create a new file called "greeting.ejs" or "greeting.handlebars" in the views folder and add the following code:

`<h1>Hello, World!</h1>`

Now, in your route handler, you can render this view and pass data to it.

```js
app.get('/', (req, res) => { 
    res.render('greeting', { message: 'Welcome to our website!' }); 
});
```

This code will render the "greeting" view and pass an object containing the message "Welcome to our website!" to it. The template engine will then use this data to fill in the placeholders in the template and create the final HTML page that will be sent to the browser.

It is also worth noting that views in Express are typically used to render dynamic content to the user. This means that views often use data from the server, such as data from a database, to populate the HTML template. For example, a view that displays a list of products would use data from a database to dynamically create the HTML for each product in the list.

Additionally, it's also possible to use a layout template that acts as a wrapper around all your views. This can be useful when you want to keep the same navigation, footer or other common elements across all views.

# Conclusion

In conclusion, we have covered the basics of templating and rendering in Express. We have discussed what templating and rendering are in the context of Express, the benefits of using a template engine, and how to set up and configure a template engine in an Express application. We also went over how to create a simple view for our simple express server and how to integrate it into the server, along with passing data to it.

It's important to note that templating and rendering in Express plays a crucial role in the development process as it allows us to separate concerns in our code and make it more organized and maintainable. It also provides a way to present data to the client in a clean and organized manner.

If you're looking to learn more about templating and rendering in Express, there are a plethora of resources available online. Some popular template engines to explore include EJS, Handlebars, and Mustache. Additionally, the official Express documentation provides a lot of useful information on the topic.

Thank you for reading this blog post. I hope you found it informative and helpful. I encourage you to share your experiences and thoughts on templating and rendering in Express. As always, thank you for being a part of my "Code, Blog, Repeat: A 50-Day Quest for Back-End Mastery" series.

> Happy Coding