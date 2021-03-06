# Authentication
---

## What is a *"Singleton"*?

**Singleton** refers to the *singleton design pattern* which is categorized as a ***creational*** design pattern. Singleton pattern is a design pattern that does nothing but define a class. The class is defined in such a manner that only one instance of the class will be created in the execution of the program.

Singletons are used where only a single instance os the class will be necessary to control action throughout the execution. They are commonly utilized for *logging, driver objects, caching* and *thread pool, database connections.*

- [GeeksforGeeks](https://www.geeksforgeeks.org/singleton-design-pattern-introduction/)

In JavaScript, the main technical advantage for singletons is *"lazy-loading"*. The singleton will only be instantiated when first needed. The potential benefits of this will be use-case specific. A singleton *might* be a good choice when:
  - it contains stateful values
  - if it memory-intensive or time-consuming to instantiate
  - if a global variable would block other more critical code

An example of a basic singleton implementation might be:

```JavaScript
class Singleton {
  constructor() {
    if (!Singleton._instance) {
      Singleton._instance = this;
    }
    return Singleton._instance;
  }
}
```

- [*"Singletons in JavaScript"*](https://medium.com/@bretcameron/singletons-in-javascript-59655927b7d7)

## How Can Singleton Pattern Classes Be Used with Node Modules?

Creating singletons in Node.JS is very simple when we utilize the Node.JS caching mechanism. modules are cached after the first time they are loaded, meaning that every call to `require('something')` will get the exact same object returned, as if resolving the same file itself.

When we finish writing a class module, we don't export the class, but rather we export an instance of the class instead. Node.JS caches and resuses this instance each time it is required. The code might look like this:

```Javascript
class Singleton {
    constructor() {
        this.message = 'I am an instance';
    }
}
module.exports = new Singleton();
```

- [*"Node.JS and Singleton Pattern"*](https://medium.com/swlh/node-js-and-singleton-pattern-7b08d11c726a)

## Approach to Building a Middleware System for Express

1. Define a function that excepts the three *"lifecycle"* methods (*request, response, next*) as arguments.
1. Execute code within the function which may or may not alter those arguments. Then end the request and response cycle in some manner or use `next()` to pass the request and response methods on to the next piece of middleware.
1. Export the custom middleware using `module.exports`
1. In `server.js` file `require` the custom middleware.

Examples of middlewares called `setCurrentUser.js`, `addNewHeader.js` and `isLoggedIn.js` that can fetch a user through authentication steps, design a new header and validate a user's data set:

***Using the `request` object***

```Javascript
const getUserFromToken = require("../getUserFromToken");

module.exports = function setCurrentUser(request, response, next) {
  const token = request.header('authorization');

  const user = getUserFromToken(token)
    .then(user => {
      request.user = user;

      next();
    });
};
```

***Applying the `response` object***

```JavaScript
module.exports = function addNewHeader(request, response, next) {
  response.setHeader('X-New-Policy', 'Success');
  next();
};
```

***Ending the `request` and `response` cycle***

```JavaScript
module.exports = function isLoggedIn(request, response, next) {
  if (request.user) {
    next();
  } else {
    response.send(401, "Unauthorized");
  }
};
```

- [*How To Create a Custom Middleware in Express.js*](https://www.digitalocean.com/community/tutorials/nodejs-creating-your-own-express-middleware)

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Router Middleware** | *Router-level middleware works in the same way as application-level middleware, except it is bound to an instance of `express.Router()`* [*"How Node JS middleware Works?"*](https://medium.com/@selvaganesh93/how-node-js-middleware-works-d8e02a936113#) |
| **Dynamic Module Loading** | *With `import()` operator we can load modules dynamically. The `import()` works like a function, but it is an operator: In order to resolve “module specifiers” relatively to the current module, it needs to know from which module it is invoked.* [*"Javascript tips — Dynamically importing ES modules with `import()`"*](https://medium.com/@leonardobrunolima/javascript-tips-dynamically-importing-es-modules-with-import-f0093dbba8e1) |
| **Singleton Pattern** | *A design pattern that does nothing but define a class. The class is defined in such a manner that only one instance of the class will be created in the execution of the program.* [GeeksforGeeks](https://www.geeksforgeeks.org/singleton-design-pattern-introduction/) |
| **Mock Testing** | *Mock testing is an approach to unit testing that lets you make assertions about how the code under test is interacting with other system modules. In mock testing, the dependencies are replaced with objects that simulate the behaviour of the real ones. The purpose of mocking is to isolate and focus on the code being tested and not on the behaviour or state of external dependencies.* [Devopedia](https://devopedia.org/mock-testing) |


### CRUD -> REST Method Matches

| **CRUD** | **REST** |
| --- | --- |
| **C**REATE | POST and PUT |
| **R**EAD | GET |
| **U**PDATE | PUT, PATCH and POST |
| **D**ELETE | DELETE |

- [*"CRUD mapping to HTTP Verbs"*](https://medium.com/@ritika.atal.work/crud-mapping-to-http-verbs-354a3c0009f5)

## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. Mock Testing
1. Router Middleware
1. The relationship between CRUD and REST

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. Hashing passwords
1. Singletons
1. Authentication in general

## I Am Most Excited About Trying to Implement or See How These Work:

- bcrypt


[Back to Main](../README.md)