# Express
---

## 3 Real World Use Cases to Change the Request with Custom Middleware

- Authenticate users
- Log the time and/or origin of the request
- Handling errors

## True or False: The Route Handler is Middleware?

After researching numerous sources including but not limited to Express.docs, GitHub, StackOverflow MDN Web Docs, there appears to be plenty debate over whether route handlers are middleware or not. The debates touch on topics such as the absence of the `next` argument, the handlers association with HTTP request verbs, whether middleware delivers a response to a request and other criteria. In my opinion, they are not middleware, they are *'handlers'* (callback functions for routes/requests), but I can not support that interpretation with any hard evidence.

#### In What Ways Can a Middleware Function End the Process and Send Data to the Browser?

- Sending a response of some type
- Throwing an error

## At What Point in the Request Lifecycle Can Middleware be “Injected”?

Middleware can be *'injected'* anytime after the request has been made and before a response has been returned. During the time that the request is *"in the tunnel"* between request and response.

## What Can Cause Express to Error with “Request headers sent twice, cannot start a second response”?

This means that for a given client request the server previously sent a response back to the client and now is unexpectedly trying to send another response to the same request. [Understanding Node Error \[ERR_HTTP_HEADERS_SENT\]](https://www.codementor.io/@oparaprosper79/understanding-node-error-err_http_headers_sent-117mpk82z8) by *Prosper Opara*

## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Middleware** | *Middleware are functions executed in the middle, after the incoming request then produces an output* [A Simple Explanation of Express Middleware](https://medium.com/@agoiabeladeyemi/a-simple-explanation-of-express-middleware-c68ea839f498) |
| **Request Object** | *The request object represents the HTTP request and has properties for the request string, parameters, body HTTP headers, and more* [TutorialsPoint](https://www.tutorialspoint.com/nodejs/nodejs_request_object.htm) |
| **Response Object** | *The response object is data returned from the server to a client following an HTTP request, and has many properties much like a request object* 
| **Application Middleware** | *Middleware that is bound to an instance of the **app object** such as `app.use()` and `app.get()` and other HTTP verbs that facilitates functionality of the application* |
| **Routing Middleware** | *Router-level middleware works in the same way as application-level middleware, except it is bound to an instance of `express.Router()` [Expressjs](https://expressjs.com/en/guide/using-middleware.html#middleware.router) |
| **Test Driven Development** | *A software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases. This is opposed to software being developed first and test cases created later.* [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development) |
| **Behavorial Testing** | *An **Agile** software development process that encourages collaboration among developers, QA and non-technical or business participants in a software project. It encourages teams to use conversation and concrete examples to formalize a shared understanding of how the application should behave.* [Wikipedia](https://en.wikipedia.org/wiki/Behavior-driven_development) |

## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. Subclasses and extending not only ES6 syntax classes but also traditional function-based "classes"
1. Route paths used with request methods not only define endpoints, but also can be comprised of strings, string-patterns or even *regular expressions*
1. Continuous Integration is a process developers use to integrate code into a shared repository where the code is verified by automated build and testing. This ensures the code is both "good" as well as able to be successfully integrated into the existing code in the repository.

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. Error-First-Callbacks
1. `express.Router()`
1. `.next()`

## I Am Most Excited About Trying to Implement or See How These Work:

- `express.Router()`


[Back to Main](../README.md)