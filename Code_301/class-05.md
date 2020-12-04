# Heroku Deployment
---
## Getting started on Heroku with Node.js

[Heroku Dev Center Getting-Started](https://devcenter.heroku.com/articles/getting-started-with-nodejs)

Above is a link to the Heroku Dev Center website with a step-by-step guide to getting started on Heroku with Node.js where a series of pages guides a user through a tutorial for deploying Node.js apps.

The tutorial guides the user through the following steps:

1. *Set up* 
   - This section explains how to make sure all of the required components are installed on the user's computer including:
     - heroku
     - node
     - npm
     - git
   Also, that new enough versions are installed.
1. *Prepare the app*
   - This section helps the user prepare a sample application to be deployed to Heroku.
     The user clones a functioning Git repository to acquire a working sample application.
1. *Deploy the app*
   - The user is instructed to create an app on Heroku and also a git remote associated with their local git repository. 
     - the app is randomly named unless a parameter is given to specify one
     - the code is then deployed by push it to heroku
     - the user ensures that an instance of the app is running and then visits the website
1. *View logs*
   - The user then learns how to view information about their running app and how to view message logs.

## Node.js

Node.js is an open source cross-platform runtime environment. It is written in JavaScript and allows us to build **server-side** and networking applications on any platform.

We can create a local server relatively easily. But we can use the **Heroku** cloud application platform to turn our server into world-wide server.

See Lenny Witman's [Node.js For Beginners...](https://howtonode.org/deploy-blog-to-heroku) website for a step-by-step guide to deploying a blog to Heroku.


[Back to Main](../README.md)