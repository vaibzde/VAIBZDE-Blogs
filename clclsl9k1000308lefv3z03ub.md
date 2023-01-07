# #Day18 - Understanding NPM (Node Package Manager)

# Introduction to NPM

NPM stands for Node Package Manager. It is a command-line tool that is used to install and manage packages (libraries or modules) in the Node.js ecosystem. NPM is the default package manager for the JavaScript runtime environment Node.js.

NPM is important because it is the default package manager for Node.js. This means that it is the go-to tool for installing and managing packages in a Node.js project. With NPM, you can easily search for and install packages from the NPM registry, manage your project's dependencies, and share your own packages with the rest of the Node.js community.

So, in this blog, we will be learning about NPM and its role in managing dependencies in a Node.js project. We will cover topics such as packages, different types of Node.js modules, and how to use NPM in a project. We will also discuss the `package.json` and `package-lock.json` files and the importance of not pushing the `node_modules` folder.

## What the heck package is?

A package is a collection of code, libraries, and resources that are bundled together and distributed as a single unit. Packages may contain one or more libraries, modules, or other resources, and are typically used to provide additional functionality or to manage dependencies in a project.

Examples of packages you may be using in your back-end projects:

* The `express` package is a popular web framework for building web applications and servers with Node.js. It provides a set of functions and middleware for handling HTTP requests and responses.
    
* The `mongoose` package is a library for interacting with MongoDB databases from Node.js applications. It provides a set of functions and schema definitions for working with MongoDB documents and collections.
    

## What is a package manager

A package manager is a tool that helps developers to manage the packages that are used in their projects. Package managers make it easy to install, update, and remove packages. They also help to ensure that all the necessary packages are installed and up to date. Some popular package managers include NPM (for Node.js), pip (for Python), and composer (for PHP).

## Definition of NPM

NPM is a **package manager** for Node.js. It is a command-line tool that allows developers to install and manage packages that are written in JavaScript. NPM also helps developers to easily share their own packages with the community.

## The role of NPM in the Node.js ecosystem

Node.js is a JavaScript runtime environment that allows developers to run JavaScript on the server-side. It is built on Chrome's V8 JavaScript engine and is designed to be lightweight and efficient. NPM is the default package manager for Node.js and plays a crucial role in the Node.js ecosystem.

NPM makes it easy for developers to install and manage packages in their Node.js projects. It also provides a platform for developers to share their packages with the community. The NPM registry, which is a public database of packages, contains over 1 million packages that are available for use.

# Types of Node.js modules

There are three types of Node.js modules: core modules, local modules, and third-party modules.

* Core modules are included with the Node.js runtime and provide core functionality. They do not need to be installed. Examples include the `fs` module for working with the file system, and the `http` module for creating HTTP servers and clients.
    
* Local modules are modules that are created by the user and are specific to a particular project. They are typically stored in a `node_modules` directory within the project.
    
* Third-party modules are created by developers outside of the Node.js project and are published to the NPM registry. They can be installed into a project using NPM and provide additional functionality. Third-party modules are often open source.
    

# Initializing an NPM Project

If you want to use the Node Package Manager (NPM) to manage dependencies and perform tasks in your project, you need to initialize an NPM project. Initializing an NPM project creates a `package.json` file in your project directory, which stores information about your project and its dependencies, as well as scripts that can be run to perform various tasks.

To initialize an NPM project, follow these steps:

1. Navigate to your project directory in the terminal.
    
2. Run the `npm init` command. This will start the process of creating a `package.json` file.
    
3. You will be asked a series of questions about your project, such as the name and version of your project. Answer these questions as prompted.
    
4. Once you have answered all the questions, a `package.json` file will be created in your project directory.
    

# Installing Packages as Dependencies in an NPM Project

There are many useful packages available on the Node Package Manager (NPM) registry that can be useful in your project. These packages may provide additional functionality, OR TO To use the functionality provided by the package in your project. such as the ability to connect to a database or send emails. To use these packages in your project, you need to install them as dependencies.

To install a package as a dependency in your NPM project, follow these steps:

1. Navigate to your project directory in the terminal.
    
2. Run the `npm install` command followed by the name of the package you want to install. For example, `npm install express` installs the Express.js package.
    
3. The package will be installed and added to the `dependencies` section of your `package.json` file.
    

That's it! The package is now installed and ready to be used in your project.

To uninstall a package using NPM, you can use the following command:

`npm uninstall [package-name]`

Using Installed Packages in an NPM Project

Once you have installed a package as a dependency in your NPM project, you can use it in your code. To use an installed package, you need to require it in your code using the `require` function.

For example, let's say that you have installed the `chalk` package, which is a library for adding color to the console output. To use it, you would first require it in your code like this:

```JS
const chalk = require('chalk');
```

This will create an instance of the `chalk` library that you can use to add color to your console output.

Here is an example of how you might use the `chalk` package to log a message in green:

```JS
const chalk = require('chalk');

console.log(chalk.green('This message is in green!'));
```

This code requires the `chalk` library and then uses the `green` method to log a message in green.

That's it! You now know how to install packages as dependencies in your NPM project and use them in your code.

# `package.json` and `package-lock.json`

When you initialize an NPM project, one of the files that is created is `package.json`. This file contains metadata about your project, such as the name, version, and description of your project, as well as a list of your dependencies and scripts.

The `package.json` file is used by NPM to manage your project's dependencies and scripts. When you install a package using NPM, it is added to the `dependencies` section of your `package.json` file. This helps you keep track of which packages your project depends on, and it allows you to easily install all of your dependencies by running a single command (`npm install`).

In addition to `package.json`, you may also see a file called `package-lock.json` in your project. This file is generated automatically when you install packages using NPM, and it contains a detailed record of the exact versions of all of your dependencies. The `package-lock.json` file is used to ensure that your dependencies are installed consistently across different environments, and it is recommended to commit this file to version control along with your `package.json` file.

### Why You Should Never Push the `node_modules` Folder to Git

When you install packages using NPM, they are downloaded and stored in a folder called `node_modules`. This folder is located in the root directory of your project, and it contains all of the packages that you have installed for your project.

The `node_modules` folder is not typically included in version control (e.g. Git), as it can be quite large and the contents of the folder are not important to the source code of your project.

Instead, the `dependencies` section of your `package.json` file is used to manage your dependencies, and the `node_modules` folder is generated automatically when you run the `npm install` command.

# Conclusion

In this blog, we have learned about NPM and its role in managing dependencies in a Node.js project. We have covered topics such as packages, different types of Node.js modules, and how to use NPM in a project. We have also discussed the `package.json` and `package-lock.json` files and the importance of not pushing the `node_modules` folder.

We hope that this blog has given you a good understanding of NPM and how it can be used to manage packages in a Node.js project. If you enjoyed this blog, please don't forget to like and subscribe to our newsletter for more informative content. We would also love to hear about your experience with NPM, so please leave a comment below.