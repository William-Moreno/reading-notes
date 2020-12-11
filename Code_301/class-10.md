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

## Error Messages and Debugging

When errors occur they tend to appear in the console. Within the overall error message, there are usually elements to help to give us some idea about the "bug" and roughly where to start looking for it. The entire message often has at least some of the following:
- whether or not the error was properly *handled*
- what type of error it is
- the line of code in which the error caused a break
- a representation of the stack at that moment (in the form of consecutive line references underneath the line in which the code broke.)

### Types of Errors

Here are some of the more common errors:

| **Type of Error** | **Example or Nature of** |
| --- | --- |
| **Reference Error** | Trying to use a variable that is not yet declared |
| **Syntax Error** | Something is wrong with the manner in which the code was entered or structured |
| **Range Error** | Manipulating an object to give it an invalid length |
| **Type Error** | Using an incompatible type of value in a statement of expression (a string where we need a number for instance) |

### Debugging

There are a number of tools available to us to utilize in debugging code:

- `console.log()` is a common simple way for us to check the values of variables at different points within the code as it executes
- Chrome developer tools can be used to tag a line and and see what has happened during execution up to that point
- a breakpoint can also be created by inserting a *debugger* statement within our code itself where we want it to break.
- we can set conditional breakpoints that will stop our programs at a point if specified conditions are met
- using Node.js with Visual Studio Code allows us to add a configuartion in the debug tab to run a debugger

### Call Stack

In an error message the call stack represents the path which the program has taken to reach the point where the break/error occured. The call stack is also available in the "sources" tab in chrome developer tools. Coupled with a debugger statement this tool allows us to step through the code.

The call stack method is significantly easier to read and ubderstand with named functions versus anonymous functions. For this reason, wherever possible functions should be named, descriptively.

`console.trace()` can also be used to see the stack track at any particular point.

### Handling Errors

Parts of the code that would execute after an error occurrs will not be executed if our errors are not *handled*. Handling errors allows us to log the error and send a fallback to the function that broke so that our code continues to execute. Our error messages will also be altered a bit, but still useful.

A popular methodology here is to use `try` ... `catch` to encapsulate problem functions and throw an error without crashing the program. The application will likely continue running, albeit with side-effects likely.

### Runtime Errors...

JavaScript is not a compiled language. This means we are often not able to see what is wrong with the code until after we run it. To save time, we can use tools like:

- ***quokka*** which evaluates code as it is typed
- ***eslint*** which makes sure our style guide is consistent and is capable of catching a few errors


Debugging and understanding error messages and how to use them is an important skill for developers. Often the only way to get better at it is to practice. This in turn should reduce the amount of time spent on subsequent debugging. Also, remember to remove debugging code from our applications before pushing them up or deploying them.


[Back to Main](../README.md)