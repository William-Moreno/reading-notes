# Express
---

## What is the Difference Between `PUT` and `PATCH`?

According to [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods), `PUT` and `PATCH` are both HTTP **request methods**. Request methods are often called *HTTP verbs*. They indicate a desired action to be performed for a given resource.

- `PUT` - The `PUT` method **replaces** all current representations of the target resource with the request payload.
- `PATCH` - The `PATCH` method is used to apply **partial modifications** to a resource.

## 3 Services/Tools to *Mock* an API for Development

According to Kristopher Sandoval's article [*"10+ Tools To Mock HTTP Requests"*](https://nordicapis.com/10-tools-to-mock-http-requests/) on Nordic APIs website, mocking HTTP requests is a vital part of testing. These tools should be able to mock common API interactions and HTTP request flows. Various tools offer differing options and implementations.

#### 3 Samples Provided in the Article

- [Nock](https://github.com/nock/nock) - an HTTP library designed to replicate and mock servers and expectations in Node.js
- [Mockserver](https://www.npmjs.com/package/mockserver) - a library that utilizes mock files in order to serve realistic mock responses. It is also highly adaptable across a wide range of options.
- [Beeceptor](https://beeceptor.com/) - a toolthat requires absolutely no code in order to utilize it. It is a free online tool for mocking a REST API interaction using any HTTP request.




[Back to Main](../README.md)