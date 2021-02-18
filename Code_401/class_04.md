# Data Modeling
---

## 3 Advantages to Test Driven Development

- You only write code that's needed
- More modular design
- Less debugging

## Use Cases for `beforeEach()` or `afterEach()` in Test Suites

If you have some work you need to do repeatedly for many tests, you can use `beforeEach()` and `afterEach()`.

For example, let's say that several tests interact with a database of cities. You have a method `initializeCityDatabase()` that must be called before each of these tests, and a method `clearCityDatabase()` that must be called after each of these tests. You can do this much more 'DRY'-ly with `beforeEach()` and `afterEach()`

- [JestJS.io Docs](https://jestjs.io/docs/en/setup-teardown)

## What is One Downside of Test Driven Development?

***Tests got to be maintained when requirements change...***

Probably, the strongest argument against TDD is that the tests need to be maintained because the code has got to. Whenever requirements change, you would like to vary the code and tests. But you’re working with TDD. this suggests that you simply got to change the tests first then make the tests pass. [*"Advantages and disadvantages of Test Driven Development (TDD)"*, GeeksforGeeks](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-test-driven-development-tdd/)

## What's the Primary Difference Between ES6 Classes and Constructor/Prototype Classes?

A class constructor creates an instance of the class. A constructor in JavaScript is just a plain old function that returns an object. The only thing special about a JavaScript constructor is that, when invoked with the new keyword, it assigns its prototype as the prototype of the returned object. 

- [*"As a JS Developer, This Is What Keeps Me Up at Night"*](https://www.toptal.com/javascript/es6-class-chaos-keeps-js-developer-up)

## Why REST?

- REST makes efficient use of bandwidth
- REST is designed to be stateless
- REST reads can be cached for better performance and scalability.
- REST predominantly uses JSON, which means better support for browser clients. 

## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Functional Programming** | *A programming paradigm that contrasts with the object orientated programming paradigm. It is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects. Functional programming is declarative rather than imperative, and application state flows through pure functions.* [Master the JavaScript Interview: What is Functional Programming?](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0#:~:text=Functional%20programming%20\(often%20abbreviated%20FP,state%20flows%20through%20pure%20functions.) |
| **Object-Oriented Programming (OOP)** | *A programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields (often known as attributes or properties), and code, in the form of procedures (often known as methods). In OOP, computer programs are designed by making them out of objects that interact with one another.OOP languages are diverse, but the most popular ones are class-based, meaning that objects are instances of classes, which also determine their types.* [Wikipedia](https://en.wikipedia.org/wiki/Object-oriented_programming) |
| **class** | *Classes are a template for creating objects. They encapsulate data with code to work on that data. Classes are in fact "special functions", and just as you can define function expressions and function declarations, the class syntax has two components: class expressions and class declarations.* [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) |
| `super` | *The super keyword is used to access and call functions on an object's parent.* [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super) |
| `this` | *The behavior of `this` in classes and functions is similar, since classes are functions under the hood. But there are some differences and caveats. Within a class constructor, `this` is a regular object. All non-static methods within the class are added to the prototype of `this`. Unlike base class constructors, derived constructors have no initial this binding. Calling  `super()` creates a `this` binding within the constructor. Derived classes must not return before calling `super()`, unless they return an `Object` or have no constructor at all.* [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) |
| **Test Driven Development (TDD)** | *A software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases. This is opposed to software being developed first and test cases created later.* [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development) |
| **Jest** | *A JavaScript testing framework with a focus on simplicity and support for large web applications. Jest does not require a lot of configuration for first time users of a testing framework.* [Wikipedia](https://en.wikipedia.org/wiki/Jest_(JavaScript_framework)) |
| **Continuous Integration** | *A development practice where developers integrate code into a shared repository frequently, preferably several times a day. Each integration can then be verified by an automated build and automated tests. While automated testing is not strictly part of CI it is typically implied.* [What is Continuous Integration?](https://www.cloudbees.com/continuous-delivery/continuous-integration) |
| **REST** | *REST (Representational State Transfer) refers to a group of software architecture design constraints that bring about efficient, reliable and scalable distributed systems. The basic idea of REST is that a resource, e.g. a document, is transferred via well-recognized, language-agnostic, and reliably standardized client/server interactions. Services are deemed RESTful when they adhere to these constraints. HTTP APIs in general are sometimes colloquially referred to as RESTful APIs, RESTful services, or REST services, although they don't necessarily adhere to all REST constraints. Beginners can assume a REST API means an HTTP service that can be called using standard web libraries and tools.* [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/REST) |
| **DATA Model** | *A data model is an abstract model that organizes elements of data and standardizes how they relate to one another and to the properties of real-world entities. For instance, a data model may specify that the data element representing a car be composed of a number of other elements which, in turn, represent the color and size of the car and define its owner.* [Wikipedia](https://en.wikipedia.org/wiki/Data_model) |

## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. SQL databases are relational databases, and the relations can be one-to-one, one-to-many and many-to-many.
1. The difference between horizontal and vertical scalability
1. "key: value" storage is a powerful tool.

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. NoSQL databases and how/when to use them vs SQL databases
1. "Hierarchial data storage"
1. What Graph databases are and how/when they are most commonly used.

## I Am Most Excited About Trying to Implement or See How These Work:

- MongoDB


[Back to Main](../README.md)