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

There is a call stack because the JavaScript engine is a single-threaded interpreter with a single call stack. *"Single-threaded"* means that it can only do one thing at a time. The call stack is fundamentally a data structure utilized to store and manage function execution temporarily and is primarily used to order or sequence the invocation of function calls. Because there is only one call stack, functions can only be operated on in sequence from the top to the bottom. This *'**L**ast **I**n, **F**irst **O**ut'* methodology is what makes the call stack **synchronous**.

*(In **asychronous** JavaScript, there is a callback function, an event loop and a task queue*)

### LIFO
The last in first out nature of the call stack can be most easily illustrated in the console when an error is thrown (intentionally or not). The error line is the function that was in process at the moment of the break. following the list of lines downward will reveal the function that called the function that broke, and below that, the any function that may have called THAT function.

### Temporary Storage

Our single-threaded interpreter can only work on whichever thing is sitting on top of the stack at any given time. The call stack is similar to an array in the aspect that as new functions are called, they are ***'pushed'*** onto the top *(or end)* of the stack, adding to the stack frame (memory). And, as these functions run to completion, they are ***'popped'*** off of the stack, clearing memory.

### Synchronicity

JavaScript maintains a record or list of the functions in memory, which is called **stack frame**, as well as their position and the order in which the functions will be executed. These elements comprise a concept known as "managing function invocation".



[Back to Main](../README.md)