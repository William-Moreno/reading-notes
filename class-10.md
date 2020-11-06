# JS Debugging

---

## Order of Execution

To find the source of an error, it helps to know how scripts are processed. The order in which statements are executed can be complex; some tasks cannot complete until another statement or function has been run:

### 2

```JavaScript
function greetUser() {
 return 'Hello ' + getName();
}
```

### 3

```JavaScript
function getName() {
 var name = 'Molly';
 return name;
}
```

### 1

```JavaScript
var greeting = greetUser();
```

### 4

```JavaScript
alert(greeting);
```

In the case above, the oder of execution is really :

- 1 - The `greeting` variable gets its value from the `greetUser()` function.
- 2 - `greetUser()` creates the message by combining the string `'Hello '` with the result of `getName()`.
- 3 - `getName()` returns the name to `greetUser()`.
- 2 - `greetUser()` now knows the name, and combines it with the string. It then returns the message to the statements that called it in _step 1_.
- 1 - The value of the `greeting` is stored in memory.
- 4 - This `greeting` variable is written to an `alert` box.

## Execution Contexts

The JavaScript interpreter uses the concept of **execution contexts**. There is one global execution context. Each function creates a new execution context and these coorespond to _variable scope_.

### Execution Context

Every script statement exists in one of three execution contexts:

1. **Global Context** - Code that is in the script, but not in a function. There is ony **one** global context in any page.
1. **Function Context** - Code that is being run within a function. Each function has its own function context.
1. **Eval Context** - Text is executed like code in an internal function called `eval()`.

### Variable Scope

The first two execution contexts correspond with the notion of scope:

1. **Global Scope** - If a variable is declared outside of a function, it can be used anywhere because it has global scope. If you do not use the `var` keyword when creating a variable, it is placed in global scope _( let, const )_
   1 **Function-Level Scope** - When a variable is declared within a function, it can only be used within that function. This is because it has function-level scope.

### The Stack

The JavaScript interpreter processes one line of code at a time. When a statement needs data from another function, it _stacks_ (or piles) the new function on top of the current task.

### Execution Context & Hoisting

Each time a script enter a new execution context, there are two phases of activity:

1. **Prepare**

   - The new scope is created
   - Variables, functions, and arguments are created

1. **Execute**
   - Now it can assign values to variables
   - Reference functions and run their code
   - Execute statements

Understanding these two phases helps to understanding the concept of **hoisting** which is what lets us:

-Call functions _before_ they have been declared (if they were created using function declarations - not function expressions)

- Assign a value to a variable that has not yet been declared.

### Understanding Scope

In the interpreter, each execution context has its own variables object. It holds the variables, functions, and parameters available within it. Each execution context can also access its parent's variables object.

### Understanding Errors and Error Objects

If a JavaScript statement generates an error, then it \*throws an **exception\***. At that point, the interpreter stops and looks for exception-handling code. If it reaches the global context without finding any , it will have to terminate the script and create an `Error` object. Error objects can help us find where our mistakes are and browsers have tools to help us read them.

When an Error object is created, it will contain the following properties:

- name
- message
- fileNumber
- lineNumber

There are seven types of built-in error objects in JavaScript:

| **OBJECT**       | **DESCRIPTION**                                                   |
| ---------------- | ----------------------------------------------------------------- |
| `Error`          | Generic error - the other errors are all based upon this error    |
| `SyntaxError`    | Syntax has not been followed                                      |
| `ReferenceError` | Tried to reference a variable that is not declared/within scope   |
| `TypeError`      | An unexpected data type that cannot be coerced                    |
| `RangeError`     | Numbers not in acceptable range                                   |
| `URIError`       | `encodeURI()`, `decodeURI()` and similar methods used incorrectly |
| `EvalError`      | `eval()` function used incorrectly                                |

#### JavaScript's 7 Different Types of Errors Examples

1. **Error**
   - Generic error object
1. **SyntaxError**
   - Syntax is not correct
     - Mismatching or unclosed quotes
     - Missing closing bracket
     - Missing common in array
     - Malformed property name
1. **ReferenceError**
   Variable does not exist
   - Variable is undeclared
   - Named function is undefined
1. **TypeError**
   Value is unexpected data type
   - Incorrect case for `document` object
   - Incorrect case for `write()` method
   - Method does not exist
   - DOM node does not exist
1. **RangeError**
   - Number outside of range
     - Cannot create array with -1 items
     - Number of digits after decimal in `toFixed()` can only be 0-20
     - Number of digits in `toPrecision()` can only be 1-21
1. **EvalError**
   - Incorrect use of `eval()` function
1. **URIError**
   - Incorrect use of URI functions
     - Characters are not escaped.

[Back to Main](README.md)
