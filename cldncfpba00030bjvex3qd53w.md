# #Day43 - Mongoose: The Ultimate Guide to Schemaless Data Modeling in MongoDB

Welcome to the 43rd day of our "Code, Blog, Repeat" series. Today we'll be diving into Mongoose, a powerful tool for data modeling in MongoDB.

### What is Mongoose?

Mongoose is an Object Document Mapper (ODM) library for MongoDB and Node.js. It provides a simple and elegant way to interact with your MongoDB database using JavaScript objects, making it easier to work with and manipulate data.

### Advantages of Using Mongoose

1. Schema Definition: Mongoose allows you to define the structure of your data using schemas, which helps enforce data integrity and consistency.
    
2. Validation: Mongoose provides built-in data validation and also allows you to create custom validators.
    
3. Middleware: Mongoose provides middleware support, which allows you to perform actions before or after certain events, such as saving or updating a document.
    
4. Query API: Mongoose provides a powerful query API, making it easy to search, sort, and filter data from your MongoDB database.
    

### Comparison with MongoDB Native Driver

While MongoDB provides a native driver for Node.js, Mongoose offers a higher-level API that provides a more convenient and user-friendly way to work with your data. Additionally, Mongoose provides built-in validation, middleware, and query support, making it a more comprehensive solution for data modeling in MongoDB.

In this guide, we'll take a closer look at the various features and capabilities of Mongoose, including how to set it up, define schemas and models, validate data, perform CRUD operations, and more.

# Setting Up Mongoose

In this section, we'll cover the basics of setting up Mongoose, including installation and configuration, connecting to a MongoDB database, and performing basic CRUD operations.

#### Installation and Configuration

To get started with Mongoose, you'll need to install it in your Node.js project. You can do this using npm (Node Package Manager) by running the following command in your terminal:

```pgsql
npm install mongoose
```

Next, you'll need to require Mongoose in your Node.js project and connect to a MongoDB database. Here's an example of how to do this:

```js
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost/test', { useNewUrlParser: true });
```

#### Connecting to a MongoDB Database

To connect to a MongoDB database, you'll need to specify the URL of your database in the `connect()` method. In this example, we're connecting to a local database named `test`.

#### Basic CRUD Operations with Mongoose

Once you've connected to your database, you can start performing basic CRUD operations with Mongoose. CRUD stands for Create, Read, Update, and Delete, and these are the four basic operations you can perform on your data.

Here's an example of how to create a new document in your database using Mongoose:

```js
const kitty = new Cat({ name: 'Zildjian' });
kitty.save().then(() => console.log('meow'));
```

In this example, we're creating a new instance of a `Cat` model and saving it to our database. You can perform similar operations to read, update, and delete data from your database.

With these basic operations, you're ready to start working with Mongoose and MongoDB. In the next section, we'll take a closer look at Mongoose schemas and models, which provide a way to define the structure and constraints of your data.

# Mongoose Schema and Models

### Understand Mongoose Schemas

Mongoose Schemas are used to define the structure of the data stored in a MongoDB collection. They work as blueprints, allowing you to specify the data fields, their types, and the rules for validating the data. A Mongoose Schema defines the shape of the documents in a collection, which includes the fields and the data types for each field. For example, you could define a schema for a blog post that has a title, body, author, and date of creation.

example:

```js
const mongoose = require("mongoose");
const Schema = mongoose.Schema;

const userSchema = new Schema({
  name: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true
  },
  password: {
    type: String,
    required: true
  },
  date: {
    type: Date,
    default: Date.now
  }
});
```

### Creating and Using Models

Once you have defined a Mongoose Schema, you can use it to create a Mongoose Model. The model is a class that represents a collection of documents in MongoDB. It provides a simple and convenient way to interact with the database by performing operations like CRUD (Create, Read, Update, Delete). For example, you can use the model to create a new document, find existing documents, update documents, and delete documents.

example:

```js
const User = mongoose.model("User", userSchema);
```

### Modifying Schemas and Models

Mongoose makes it easy to modify Schemas and Models as your application evolves. You can add new fields, change data types, and update validation rules to reflect changes in your data requirements. Mongoose also supports versioning, so you can keep track of changes to your Schemas and Models over time.

example:

```js
userSchema.update({ name: { type: String, required: true } }, { age: { type: Number, required: true } });
const User = mongoose.model("User", userSchema);
```

### Creating the database and collection in MongoDB programmatically

In MongoDB, databases and collections are created automatically when you insert a document. With Mongoose, you can create a database and collection programmatically by simply creating a model and saving a document. Mongoose will automatically create the database and collection if they don't already exist.

Here's an example of how to create a database and collection programmatically using Mongoose:

```js
// import Mongoose
const mongoose = require('mongoose');

// connect to the MongoDB database
mongoose.connect('mongodb://localhost/testDB', { useNewUrlParser: true, useUnifiedTopology: true });

// create a schema
const userSchema = new mongoose.Schema({
    name: { type: String, required: true },
    age: Number
});

// create a model
const User = mongoose.model('User', userSchema);

// create a new user document
const newUser = new User({ name: 'John Doe', age: 30 });

// save the document to the database
newUser.save((error) => {
    if (error) {
        console.log(error);
    } else {
        console.log('User added successfully!');
    }
    // close the connection to the database
    mongoose.connection.close();
});
```

In this example, we first connect to a MongoDB database using `mongoose.connect`. The `testDB` database is created if it doesn't already exist. We then define a schema using `mongoose.Schema` and create a model using `mongoose.model`. A new user document is then created using the `User` model, and the document is saved to the database using the `save` method. Finally, we close the connection to the database using `mongoose.connection.close`.

### Putting inbuilt constraints on the model schema

Mongoose provides several built-in validators that you can use to validate the data stored in your documents. For example, you can use the required validator to ensure that a field must be present in every document, or the minlength validator to enforce a minimum length for a string field. By using these built-in validators, you can ensure that the data stored in your MongoDB collection is valid and consistent.

example:

```js
const userSchema = new Schema({
  name: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true
  },
  password: {
    type: String,
    required: true,
    min: 8,
    max: 32
  },
  date: {
    type: Date,
    default: Date.now
  }
});
```

### Using Built-in Validators:

Mongoose provides several built-in validators that can be used to enforce constraints on the data stored in the database. These built-in validators include constraints like type checking, required fields, maximum length, minimum length, and more. These validators are specified as options in the schema definition. Example:

```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const userSchema = new Schema({
    name: {
        type: String,
        required: true,
        minlength: 3,
        maxlength: 50
    },
    email: {
        type: String,
        required: true,
        unique: true,
        validate: {
            validator: function(value) {
                return /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/.test(value);
            },
            message: 'Email is invalid'
        }
    },
    password: {
        type: String,
        required: true,
        minlength: 8,
        maxlength: 1024
    },
    date: {
        type: Date,
        default: Date.now
    }
});

const User = mongoose.model('User', userSchema);

module.exports = User;
```

In this example, we are defining a user schema with several fields like `name`, `email`, `password`, and `date`. For each field, we are using built-in validators to enforce constraints on the data stored in the database. For example, the `name` field must be a string with a minimum length of 3 and a maximum length of 50, the `email` field must be a string, required, unique and match the email format, and the `password` field must be a string with a minimum length of 8 and a maximum length of 1024. Additionally, we are setting the `date` field to be a Date type with a default value of the current date and time.

### Creating custom validators for the model schema

In addition to the built-in validators, Mongoose also allows you to create custom validators. Custom validators give you greater control over the data stored in your documents by allowing you to write your own validation logic. For example, you could write a custom validator to enforce a maximum length for a string field, or to validate the format of an email address.

Let's say we want to create a custom validator to ensure that the "email" field in our user model is a valid email address. We can do this by creating a custom validation function and passing it as an argument to the email field in the schema.

```js
const userSchema = new mongoose.Schema({
  email: {
    type: String,
    required: true,
    validate: function(value) {
      return /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(value);
    }
  }
});
```

In this example, the custom validator is a regular expression that tests the value of the "email" field to see if it matches the pattern of a valid email address. If the value does not match the pattern, the validator will return false and the user document will not be saved.

# Working with Mongoose Queries

Mongoose provides a simple and elegant way to work with queries in MongoDB. The Mongoose Query API offers a wide range of methods for performing common database operations such as reading, updating, and deleting data. Let's take a look at some of the most commonly used Mongoose query methods.

### Common Mongoose Query Methods

* `find`: Returns an array of all the documents in a collection that match the specified query.
    
* `findOne`: Returns the first document that matches the specified query.
    
* `findById`: Returns the document with the specified ID.
    
* `where`: Returns an array of all the documents in a collection that match the specified query.
    
* `sort`: Sorts the results of the query in ascending or descending order.
    

In addition to these common methods, Mongoose also supports advanced queries and aggregation operations such as filtering, grouping, and transforming data. These operations can be performed using the MongoDB Aggregation Pipeline.

### Advanced Queries and Aggregation with Mongoose

Mongoose supports the use of the MongoDB Aggregation Pipeline, allowing you to perform advanced operations such as filtering, grouping, and transforming data. This is done by calling the `aggregate` method on a model and passing an array of aggregation stages.

### Understanding CRUD operations

CRUD stands for Create, Read, Update, and Delete, and it represents the four basic database operations. With Mongoose, you can perform these operations using the methods we discussed in the Common Mongoose Query Methods section.

#### Implementing CRUD operations in a MongoDB database using Mongoose

Now that we have a basic understanding of the Mongoose Query API, let's see how we can implement CRUD operations in a MongoDB database using Mongoose.

Here's an example of how to create a new document in a collection using Mongoose:

```js
const mongoose = require("mongoose");
const { Schema } = mongoose;

const UserSchema = new Schema({
  name: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true
  }
});

const User = mongoose.model("User", UserSchema);

// Creating a new document in the collection
const user = new User({
  name: "John Doe",
  email: "johndoe@example.com"
});

user.save((error) => {
  if (error) {
    console.error(error);
  } else {
    console.log("User created successfully");
  }
});
```

Here's an example of how to read documents from a collection using Mongoose:

```js
User.find({}, (error, users) => {
  if (error) {
    console.error(error);
  } else {
    console.log(users);
  }
});
```

Here's an example of how to update a document in a collection using Mongoose:

```js
User.findOneAndUpdate(
  { name: "John Doe" },
  { name: "Jane Doe" },
  { new: true },
  (error, updatedUser) => {
    if (error) {
      console.error(error);
    } else {
      console.log(updatedUser);
    }
  }
);
```

Here's an example of how to delete a document in a collection using Mongoose:

```js
User.deleteOne({ name: "Jane Doe" }, (error) => {
  if (error) {
    console.error(error);
  } else {
    console.log("User deleted successfully");
  }
});
```

Note that in these examples, we are using the `User` model that we created earlier to perform CRUD operations on the `User` collection in the MongoDB database.

# Mongoose Middleware and Plugins

Mongoose provides a way to add middleware to your models, which allows you to run certain code before or after various events, such as saving, updating, or deleting a document. This is a powerful feature that can be used to add custom logic, audit trails, and more.

In this section, we will cover the basics of Mongoose middleware and how to use plugins to extend the functionality of your models.

### Overview of Mongoose Middleware

Mongoose middleware allows you to add code that runs before or after certain events, such as saving or deleting a document. This code can be used to add custom logic or audit trails, or to modify the document in some way.

Mongoose middleware is defined as a function that takes two arguments: the current document and the next middleware function to be called. When the middleware is complete, you must call the next function to continue processing.

There are two types of middleware in Mongoose: pre and post. Pre middleware runs before an event, while post middleware runs after an event.

### Using Mongoose Plugins to Extend Functionality

Mongoose plugins are a way to extend the functionality of your models. A plugin is simply a JavaScript module that exports a function. This function takes a Mongoose schema as an argument and can make modifications to the schema.

Plugins are a great way to add custom functionality to your models without having to write it directly in your code. They can be used to add custom validation, add virtual properties, and more.

### Implementing Middleware and Plugins in a Project

Now that we have a basic understanding of Mongoose middleware and plugins, let's see how we can implement them in a project.

First, let's see how to implement middleware in a project. This can be done by defining a middleware function and attaching it to a model using the .pre() or .post() method.

Example:

```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const mySchema = new Schema({
  name: String,
  date: Date
});

mySchema.pre('save', function(next) {
  this.date = new Date();
  next();
});

const MyModel = mongoose.model('MyModel', mySchema);
```

In this example, we are using the .pre('save') method to attach a middleware function to the MyModel model. This function sets the date property to the current date and time before saving the document.

Next, let's see how to implement a plugin in a project. This can be done by creating a JavaScript module that exports a function and then including that module in your project.

Example:

```js
// plugin.js
module.exports = function(schema) {
  schema.add({ createdAt: Date });

  schema.pre('save', function(next) {
    this.createdAt = new Date();
    next();
  });
};

// myModel.js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;
const plugin = require('./plugin');

const mySchema = new Schema({
  name: String
});

mySchema.plugin(plugin);

const MyModel = mongoose.model('MyModel', mySchema);
```

In the above code, we have created a plugin that adds a "createdAt" field to the document and sets its value to the current date and time when the document is saved. To use the plugin, we simply call the `.plugin()` method on our schema and pass in the exported function from the plugin.js file.

In this way, plugins provide a simple and flexible way to extend the functionality of Mongoose models. They can be used to add additional fields, manipulate data, or even create entirely new functionality.

# Conclusion

In conclusion, we have covered the basics of Mongoose middleware and plugins and seen how they can be used to extend the functionality of Mongoose models.

Key takeaways from this article include the understanding of Mongoose middleware, which runs code before or after events such as saving or deleting a document, and Mongoose plugins, which are modules that export functions to modify the schema of a Mongoose model.

Mongoose is a powerful tool for working with MongoDB and provides a convenient way to model your data and add custom logic. We hope this article has provided a solid foundation for using Mongoose middleware and plugins in your projects.

As always, I encourage you to like, share, and comment on this post if you found it helpful. This post is part of our "Code, Blog, Repeat: A 50-Day Quest for Back-End Mastery" series where I am sharing experiences and insights on advanced concepts and technologies related to Backend Development.