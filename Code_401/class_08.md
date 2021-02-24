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

- [*"SECURITY ISSUES IN JWT AUTHENTICATION"*](https://www.softwaresecured.com/security-issues-jwt-authentication/)

## Vocabulary Terms
| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Encryption** | *The process of encoding information. This process converts the original information, known as plaintext, into an alternative form known as ciphertext. Ideally, only authorized parties with a "pseudo-random", algorithm generated encryption key can decipher a ciphertext back to plaintext and access the original information.* [*Wikipedia*](https://en.wikipedia.org/wiki/Encryption) |
| **Token** | *A token is necessary for authentication for some servers that is created and provided by the server. Some servers will issue tokens that are a short string of hexadecimal characters, while others may use structured tokens such as JSON Web Tokens.* [*oauth.net*](https://oauth.net/2/bearer-tokens/) |
| **Bearer** | *This is the user/client that is in possession of a server-issued "token" of some kind which provides them access to specified data/information on/from that server.* |
| **Secret** | *A key known only to the server, meaning only the server can issue keys with a valid signature. Tokens cannot be forged with a valid signature without knowledge of the SECRET.* [*"SECURITY ISSUES IN JWT AUTHENTICATION"*](https://www.softwaresecured.com/security-issues-jwt-authentication/) |
| **JSON Web Token** | *An open standard that defines a way for securely transmitting information, in the form of a JSON object, between clients and servers in a self-contained and compact manner.* [*Introduction to JSON Web Tokens*](https://jwt.io/introduction) |


## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. RBAC is based on varying levels of system access based on an individual's role within an organization
1. RBAC systems break down quickly when exception/"one-off" roles are created for individuals
1. RBAC is a computer systems security approach to restricting system access to authorized users, allowing users of differing defined roles access to only the parts of the system, or resources, they require in their assigned role

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. A methodical way to approach implementing RBAC
1. How complex RBAC systems can become based on the number of possible roles and possible resources available in a given organization
1. Are roles' server access controlled "internally" by issuing specific tokens? or by accessing sometype of database structure?

## I Am Most Excited About Trying to Implement or See How These Work:

- Trying to set up an RBAC system

[Back to Main](../README.md)


