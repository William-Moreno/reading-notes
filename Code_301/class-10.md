# The Call Stack and Debugging
---
## Call Stack

A **call stack** is a model that interpreters use to arrange script functions for execution and keep their sequence ordered. A basic example of this flow would be:

    - As a function is called by the script, it is added to the interpreter's stack and the interpreter starts carrying the function out
    - If the function being executed calls a new function, or functions, in its script, it or they are added to the top of the stack
    - Progress on the invoking function is suspended and the function now located on top of the stack is executed, possibly calling a further function that would be placed on top of it and therefore take priority
    - After the top most function resolves in full, it is removed from the stack and the interpreter resumes working on the function that called it or returns to executing lines of code, until a subsequent function is called


  - *If the current stack ever exceeds the space alotted to hold it the result is a **"stack overflow"** error*.

### Why is there a call stack?

There is a call stack because the JavaScript engine is a single-threaded interpreter with a single call stack. This call stack is primarily used to invoke function calls. Because there is only one call stack, functions can only be operated on in sequence from the top to the bottom. This *'**L**ast **I**n, **F**irst **O**ut'* methodology is what makes the call stack **synchronous**.



[Back to Main](../README.md)