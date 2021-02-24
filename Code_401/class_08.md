# Access Control
---

## Basic Authorization vs. Bearer Authorization

Basic Authentication is a string-based form of authentication in which the user submits a username, password combination. This information is encoded and sent in the header of a request which is recieved by the server and decoded to authenticate the user and return some form of data/information/thing. It is not as secure of a method as Bearer Authentication. 

Bearer Authentication is a token-based form of authentication in which a user submits credentials much the same as Basic Authentication to request a token from the server. The *'signed'* token is comprised of a header, payload and a signature. Upon being assigned, or receiving a token from the server, the client can then use that token to access portions of the server that require Bearer Authorization. This more protected data/information/thing is then returned to the client making the request with the proper token in the header. 

## What Does the JSON Web Token Package Do?

JSON Web Token *(JWT)* is an open standard that defines a way for securely transmitting information, in the form of a JSON object, between clients and servers in a self-contained and compact manner. The information is digitally signed and can be verified.

- [*Introduction to JSON Web Tokens*](https://jwt.io/introduction)

## What Constiderations Should We Make When Creating and Storing a SECRET?

The 'SECRET' is a key known only to the server, meaning only the server can issue keys with a valid signature. Tokens cannot be forged with a valid signature without knowledge of the SECRET. As such, this SECRET should be kept in a private area and never anywhere that might be visible to the public/client.




