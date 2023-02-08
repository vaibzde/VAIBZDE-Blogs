# #Day50  - Deploying a NodeJS Application on a Server: A Guide

Wow, what a journey it has been! Today marks the end of our 50-day challenge "Code, Blog, Repeat: A 50-Day Quest for Back-End Mastery." And what a fitting way to end it by discussing the exciting topic of deploying a NodeJS application on a server.

Deploying a NodeJS application on a server simply means taking the code you have developed and making it accessible to the world through the internet. This process involves setting up the development environment, connecting it to a database, and making it accessible through a domain name.

In this blog, we'll be covering all the necessary steps to deploy your NodeJS application, from setting up a repository on Github to registering a domain name. We'll also be exploring the benefits of deploying your application and why it's an important step for any backend developer.

So, let's get started and end this series on a high note!

# Understanding Hosting

Hosting is an essential aspect of deploying a NodeJS application on a server. It refers to the process of making your application accessible to the world through the internet. When you host an application, you are essentially renting space on a server that is connected to the internet. This allows users to access your application from anywhere in the world.

One of the main differences between running a project locally and deploying it on a server is the environment. When you run a project locally, it is only accessible on your own computer or device. When you deploy it on a server, it becomes accessible to anyone with an internet connection.

Another important difference between running a project locally and deploying it on a server is the level of control you have over the environment. When you run a project locally, you have complete control over the environment, including the operating system, tools, and software. When you deploy an application on a server, you are limited by the resources and tools provided by the hosting provider.

To understand hosting in the context of deploying a NodeJS application, it is important to understand the different types of hosting available. The most common types of hosting include shared hosting, virtual private servers (VPS), and dedicated servers. Each of these hosting options has its own advantages and disadvantages, and it is important to choose the right option based on the requirements of your application.

# Setting up the Development Environment

The development environment is the environment in which a software application is created, developed, and tested. In the context of deploying a NodeJS application on a server, setting up a development environment is important because it provides a place to write, test, and debug the application before deploying it to a production environment.

Creating a repository on Github is a crucial step in setting up the development environment because it provides a place to store the source code and track changes to the code over time. The repository is also the place where the application is stored before deploying it to a server.

#### Steps for creating a repository on Github for the NodeJS application:

1\. Go to Github and sign up or log in to your account. 2. Click on the "+" symbol on the top right corner of the page and select "New repository." 3. Give your repository a name that is related to your NodeJS application and select "Create repository." 4. Once your repository is created, you can initialize it with a README file, a .gitignore file, or a license. 5. Add your NodeJS application files to the repository by either using the command line or the drag and drop feature on Github.

#### Explanation of the importance of version control when deploying applications:

Version control is an essential aspect of deploying applications, as it enables you to keep track of changes made to your code, collaborate with others, and revert to previous versions if necessary. When deploying a NodeJS application, it is important to use version control so that you can easily manage and maintain the code, keep track of changes, and ensure that your application is always up-to-date and functioning as intended. With version control, you can also keep a history of your code, which can be helpful for debugging and troubleshooting any issues that may arise in the future.

#### Setting up a Database

When deploying a NodeJS application, a database is an essential component to store and manage data. In this blog series, we have used MongoDB as an example to demonstrate the setup process. However, if you are using a different database, the steps to set it up may vary. Regardless of the database you choose, the importance of having a proper database setup remains the same.

When building a backend application, it is common to use a local database like the MongoDB Community version during the development process. However, in order to make the application accessible to a wider audience, a cloud-based database is necessary.

MongoDB Atlas is a cloud-based database service that makes it easy to set up and manage a MongoDB database. By using MongoDB Atlas, you can benefit from features such as automatic backups, scaling, and monitoring, without having to worry about the underlying infrastructure.

To set up a database on MongoDB Atlas, the following steps are involved:

1. Create an account on the MongoDB Atlas website.
    
2. Create a new project.
    
3. Create a new cluster.
    
4. Whitelist your IP address to allow access to the cluster.
    
5. Connect to the cluster using a connection string.
    
6. Verify that the connection to the cluster is working by inserting data into a collection.
    

By following these steps, you can easily set up a database for your NodeJS application on MongoDB Atlas, allowing you to focus on building your application and not worry about managing the underlying database infrastructure.

# Deploying on Heroku

In this section, we'll take a look at deploying a NodeJS application on Heroku. Heroku is a popular cloud platform that makes it easy to deploy, run, and manage applications written in multiple programming languages, including NodeJS.

### Introduction to Heroku

Heroku is a cloud platform as a service (PaaS) that enables developers to build, run, and operate applications entirely in the cloud. Heroku offers a simple and intuitive platform for deploying, managing, and scaling applications without the need for infrastructure management. With its easy-to-use platform and a wide range of features and services, Heroku has become a popular choice among developers for deploying NodeJS applications.

#### What is Heroku and What Does it Do?

Think of Heroku as a superhero who swoops in to save the day for developers looking to deploy their applications. Heroku is a cloud platform that provides a simple, easy-to-use, and fast way to deploy, manage, and scale web applications. The platform abstracts away the complexities of server management, allowing developers to focus on writing code and building great applications.

#### Steps to Deploying a NodeJS Application on Heroku

###### Setting up the Heroku account

To deploy your NodeJS application on Heroku, you first need to create an account. This is a straightforward process, and you can sign up for an account using your email address.

###### Connecting the Github repository to Heroku

Once you have set up your Heroku account, you need to connect it to your Github repository. This allows Heroku to access your code and deploy it to its servers. You can do this by following these steps:

1. Go to the Heroku dashboard and click on the “New” button.
    
2. Select “Create new app” and give your app a name.
    
3. Scroll down to the “Deploy” section and click on the “Github” option.
    
4. Search for your Github repository and connect it to Heroku.
    

###### Deploying the application through the Heroku CLI

Now that you have connected your Github repository to Heroku, you can deploy your application. To do this, you will use the Heroku CLI, a command-line interface that allows you to interact with Heroku from your terminal. To deploy your application, follow these steps:

1. Open your terminal and navigate to your project’s root directory.
    
2. Run the command `heroku login` to log in to your Heroku account.
    
3. Run the command `git push heroku master` to deploy your application.
    

> To deploy an ExpressJS application on Heroku, you'll need to create a `Procfile` in the root directory of your application. The `Procfile` tells Heroku how to start your application.

To see some of the best practices and examples of deploying NodeJS applications on Heroku, you can check out the Heroku Dev Center. This is a great resource for learning more about deploying NodeJS applications on Heroku and getting inspiration for your own deployments.

## Other Options Besides Heroku

While Heroku is a popular platform for deploying NodeJS applications, it's not the only option available. Other platforms that you can consider include AWS Elastic Beanstalk, Microsoft Azure, and Google Cloud Platform. Each platform has its own strengths and weaknesses, so be sure to research and compare them before making a decision.

# Domain Name Registration and URL Setup

A domain name is a unique name that identifies a website and makes it easily accessible to users. It is the web address people type into the browser to access your website. Domain name registration is the process of registering a domain name for your website. This helps ensure that no one else can use the same name and gives you the rights to use it for a specific period of time.

To register a domain name, you can follow these steps:

1. Choose a domain name that represents your website and is easy to remember
    
2. Find a domain name registrar such as GoDaddy or Namecheap
    
3. Search for the domain name to see if it is available
    
4. If it is available, complete the registration process by providing your contact information and paying the fee
    

URL setup refers to the process of pointing your domain name to the IP address of your website. This allows users to access your website by typing in the domain name instead of the IP address. URL setup is important because it makes it easier for users to remember and access your website.

To set up the URL, you can follow these steps:

1. Log into your account with the domain registrar
    
2. Go to the “DNS Management” section
    
3. Add a new record for the domain name, specifying the IP address of your website &gt; The IP address of a website can be obtained from the deployment platform such as Heroku. Once you deploy your NodeJS application on Heroku, it assigns a unique IP address to the website, which can be used to set up the URL.
    
4. Save the changes and wait for the changes to take effect (it may take up to 24 hours for the changes to propagate)
    

By using a domain name and URL setup, it becomes easier for users to access and remember your website, making it more accessible and user-friend

# Accessing the Deployed Application

Accessing the deployed application means retrieving the application from the server and making it available for use. This is done after the application has been deployed on a platform like Heroku or any other hosting platform.

Steps for accessing the deployed application:

1. Log in to the platform where the application was deployed.
    
2. Locate the deployed application in the platform's dashboard.
    
3. Click on the link or URL provided to access the application.
    

Accessing the deployed application is important because it enables you to view the application and make sure it is working as expected. It allows you to test the application, fix any bugs and make any necessary updates. This is crucial for ensuring that the application is working optimally before making it available to the public.

# Conclusion

In conclusion, we have covered a wide range of topics in this series of blogs on back-end mastery. From setting up a NodeJS environment to working with databases and deploying applications, this series aims to provide comprehensive information for anyone looking to master back-end development.

Here is Vaibhav Dewangan, I am a student of back-end dev and tech, who has shared his knowledge and experience in these blogs.

Thank you for reading this series and joining the journey of back-end mastery. I hope that you have learned something new and useful. If you haven't read the full series yet, you can find it at [https://vaibzde.hashnode.dev/series/50-day-back-end-mastery](https://vaibzde.hashnode.dev/series/50-day-back-end-mastery).

I would be happy to connect with you on LinkedIn at [https://www.linkedin.com/in/vaibhavdewangan/](https://www.linkedin.com/in/vaibhavdewangan/) and Twitter at [https://twitter.com/vaibzde](https://twitter.com/vaibzde). Don't forget to sign up for the newsletter to stay updated on future blog posts. Happy learning!