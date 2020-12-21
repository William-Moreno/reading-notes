# Update/Delete
---
## Sending Form Data

The following notes are compiled from [MDN web docs mozi*ll*a](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)...

### Client/Server Architecture

Fundamentally, the web utilizes a client/server architecture summarized as:

1. a *client* *(typically a web browser)* uses HTTP protocol to send a request to a server
1. The server *(usually a web server, such as Apache or Tomcat...)* uses the same protocol to answer that request


HTML web page forms are merely a easy method to create/configure/dispatch a HTTP request to send data to a server. They allow users to provide and organize data to be delivered to that server.

### Client Side

The form's `action` attribute is the target destination for the its data. It should be assigned an absolute URL or a valid relative as a value. Without one, the form data will be sent to the current page. Examples might be:
```html
<form action="https://example.com">
```

or

```html
<form action="/somewhere_else">
```

### Method

How data is sent is defined by the `method` attribute. There are several ways to send these requests in HTTP protocol. The two most common are `GET` and `POST`.

#### GET

Browsers use the `GET` method to ask servers to send back desired resources. When GET is used, the browser essentially sends an empty web page with the actual form data appended to the URL of that empty page. We are able to see they actual form data on the address line in our browsers, organized as a series of key/value pairs. These pairs are separated from the URL web address by a `?` and chained together using `&`s.

#### POST

Conversely, when browsers use the `POST` method, the data being sent to the server is appended to the body of the dispatched HTTP request. The URL displayed in our browser address bars is unchanged and shows no key/value pairs. Though, headers like `Content-Length` and `Content-Type` can give you a clue about the size kind of information is contained.

### Viewing HTTP Requests

HTTP requests are never displayed to the user. Although, the users can see what the URL is called. As previously stated, data for a `GET` request will be visible in the URL. Data sent with a `POST` will not. With that in mind:

1. Never send passwords or other sensitive data using the `GET` method.
1. When we need to send large amounts of data, the `POST` method is preferred because some browsers and/or servers limit the sizes of URLs.

### Server Side

Regardles of which method is used to send the data, the server receives that data as a string which must be parsed to reconstitute a list of key/value pairs. The method by which this accomplished and this list is accessed varies from platform to platform and framework to framework. Frameworks, such as Express, save us time working with forms because they save us from having to write all of the functionality ourselves.



[Back to Main](../README.md)