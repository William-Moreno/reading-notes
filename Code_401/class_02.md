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

## Compare and Contrast Swagger and APIDoc.js

| **Swagger** | **APIDoc.js** |
| --- | --- |
| creates documentation for API | creates documentation for API |
| requires that implemented methods be documented with custom comment data | requires that implemented methods be documented with custom comment data |
| uses OpenAPI specification to work | creates documentation from API annotations in source code |
| [Swagger Documentation](https://swagger.io/docs/) | [APIDoc.js](https://swagger.io/docs/) |


## Which HTTP Status Codes Should Be Sent with Each Type of (Un)Successful API Call?

According to [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status), HTTP response status codes are grouped into 5 classes:

1. Informational responses (`100` - `199`)
1. Successful responses (`200` - `299`)
1. Redirects (`300` - `399`)
1. Client errors (`400` - `499`)
1. Server errors (`500` - `599`)

## Compare and Contrast SOAP and ReST

The following information is derived from the 2017 Stackify article [*"SOAP vs. REST: The Differences and Benefits Between the Two Widely-Used Web Service Communication Protocols"*](https://stackify.com/soap-vs-rest/) by Alexandra Altvater.

SOAP was the standard approach to web service communication protocols for a long time but it has been dominated by REST in recent years. REST now represents over 70% of public APIs.

| **SOAP** | **ReST** |
| --- | --- |
| **S**imple **O**bject **A**ccess **P**rotocol | **Re**presentational **S**tate **T**ransfer |
| performs operations through messaging patterns | simply accesses data |
| provides more robust security and support for identity verification | allows greater variety of data formats |
| offers built in logic to compensate for failed communications | generally considered easier to work with |
Tends to be slower because it uses the complex XML format | generally faster and uses less bandwidth and easier to integrate with existing websites |





[Back to Main](../README.md)