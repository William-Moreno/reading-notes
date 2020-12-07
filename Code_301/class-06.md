# Node, Express and APIs
---
## Node

Node.js is a program people can use to execute JavaScript on their computers. After installing Node in our terminals, we can check which version we have installed on our system by typing:
```
node --version
```
If we have Node properly installed and configured, we can run simple programs to display messages in the terminal window. Pressing ctrl+c will escape the terminal console.

Node has good support for modern JavaScript. Our JavaScript can be written using the most current syntax. Generally speaking, we will not have to worry about compatibility issues.

We can use npm (node package manager) to install packages locally.
```
npm init -y
```
This command will create and auto-populate a package.json file in the current directory.

This use of npm is actually one of the first common uses for Node. Various build tools are installed using npm and the run using Node.

### Common Reasons to Learn Node.js

A working knowledge of Node.js is requisite to developing apps in React and Angular (for instance). This is because these frameworks are all delivered via npm and rely on Node to create an environment they can run in.

One of the biggest reasons to use Node is that it allows the use of JavaScript on the server. As such, it is used by many high-profile companies in their stacks.

Traditional servers are "muti-threaded" in basis. This tands to be less efficient than the Node alternative, and can cause the system to become sluggish or to go down. The answer to more traffic, or use, is typically to add more servers to the system.

Node, on the other hand, is single-threaded and event-driven. Meaning that events trigger everything that happens in Node. Node uses the **libuv** library to implement **asynchronous** behavior. This means that Node systems are capable of handling large numbers of simultaneous connections. To scale up for more traffic, or use, the common method is to clone the Node app, using a built in module, using it to handle more connections and traffic.

According the the sitepoint web page "What Is Node and When Should I Use It?" by James Hibbard, Node's execution model is:

1. Node apps pass asynchronous tasks to the event loop along with a callback
1. The event loop efficiently manages a thread pool and executes tasks efficiently
1. and executes each callback as tasks complete

### Downsides?

- Blocking I/O calls should be avoided
- CPU-intensive operations should be handled by 'woorker' threads
- Errors should always be handled correctly or they might lead to a crash







[Back to Main](../README.md)