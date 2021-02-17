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
| **Middleware** | *A web server is a piece of software that often runs on a hardware server offering service to a user, usually referred to as the client* [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Glossary/Web_server) |
| **Request Object** | *Express is the most popular Node web framework, and is the underlying library for a number of other popular Node web frameworks* [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction) |
| **Response Object** | *Routing is the mechanism by which requests are connected to some code. It is essentially the way you navigate through a website or web-application.* [Wilbert Schepenaar](https://medium.com/@wilbo/server-side-vs-client-side-routing-71d710e9227f) |
| **Application Middleware** | *'Web Request/Response Cycle'* *The web is a cycle of requests and responses that flow between clients and servers.* [Jen Strong](https://medium.com/@jen_strong/the-request-response-cycle-of-the-web-1b7e206e9047) |
| **Routing Middleware** |  |
| **Test Driven Development** |  |
| **Behavorial Testing** |  |

## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. Node.js is a **runtime environment** intended for use OUTSIDE of a browser context
1. Express.js is a Node web **framework** that allows us to write handlers for requests using HTTP verbs and routes and utilize view rendering engines to generate templated responses
1. Continuous Integration is a process developers use to integrate code into a shared repository where the code is verified by automated build and testing. This ensures the code is both "good" as well as able to be successfully integrated into the existing code in the repository.

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. Error-First-Callbacks
1. `express.Router()`
1. `.next()`

## I Am Most Excited About Trying to Implement or See How These Work:

- Object Relational Mappers (ORM)
- Additional view rendering templates


[Back to Main](../README.md)