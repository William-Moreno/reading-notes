# Refactoring
---
## Functional Programming

According to Wikipedia:

> Functional programming is a programming paradigm - a style of building the structure and elements of computer programs - that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

### Pure Functions

A pure function returns the same result if given the same arguments and does not cause any side effects which can be observed.

Our functions should make use of parameters passed into them, and not access external objects to perform their jobs. When the function is passed the same parameters, they will always generate the same results.

Functions which read external files can never be pure, because those external files' contents can and often do change.

Functions that rely on random number generation cannot be pure because they will not always generate the same results.

Observable side effects often includes the modification of global objects or parameters which were passed by reference.

In impure function may be passed a global variable as a parameter and then alter or reassign the value of that global variable while resolving.

The difference can be illustrated with the following examples:

```JavaScript
let count = 5;

function quintuple(value) {
  count = value * 5;
}

quintuple(count);
console.log(count);  // 25
```
```JavaScript
let count = 5;

const quintuple = (value) => value * 5;

quintuple(count); // 25
console.log(count); // 5
```
The first of these receives the `count` value and reassigns `count` from a value of 5 to a value of 25.

**Mutability is discouraged in functional programming**

In the second instance, the function simply returns the value multiplied by 5 without altering the original value of the variable.

Every function should be isolated and unable to impact other parts of the system. Pure functions are:
- Stable
- Consistent
- Predictable

Another benefit of pure functions is that they are significantly easier to test.

### Immutability

Immutabilty is defined as *unchanging over time or unable to be changed*.

The state of **immutable data** *cannot* changed after it is created/declared. Since we cannot change an immutable object, we would have to create a *new* object with the desired new value.

The next two examples are taken from *The Renaissance Developer*'s article [***Concepts of Functional Programming in JavaScript***](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa):

```JavaScript
var values = [1, 2, 3, 4, 5];
var sumOfValues = 0;

for (var i = 0; i < values.length; i++) {
  sumOfValues += values[i];
}

sumOfValues // 15
```

```JavaScript
let list = [1, 2, 3, 4, 5];
let accumulator = 0;

function sum(list, accumulator) {
  if(list.length == 0) {
    return accumulator;
  }

  return sum(list.slice(1), accumulator + list[0]);
}

sum(list, accumulator); // 15
list; // [1, 2, 3, 4, 5]
accumulator; // 0
```

In the first case, while iterating with a for loop, we are changing the states of the `i` variable and the `sumOfValues` variable. To avoid mutability in iteration, we use **recursion**.

In the second example, the function calls itself until the list is empty (reaching the recursion base case set by `if(list.length == 0) {return accumulator;}` In each iteration, we add the value to the `total` accumulator.

Recursion allows us to keep our variables immutable. In the second case above the `list` and `accumulator` variables remain unchanged. The retain their original values.

### Referential Transparency

When we combine pure functions with immutable data the result is referential transparency. Fundamentally, if a function returns the same result for the same input consistently, it is referentially transparent and often times can be a candidate for **memoization**.

If an expression consistently returns the same numerial value, it can be replaced by a numerical constant.

## First-Class Entities

The concept of functions being first-class entities refers to the practice of using functions as data and treating them as values.

- We can refer to them from constants and variables
- We can pass them as arguments into other functions
- We can return them from other functions as results

In this manner, we can combine different functions in different ways to create new functions with new behavior.

## Higher-Order Functions

A higher order function either:
- takes a function or functions as arguments, and/or
- returns a function as its result

### Filter




[Back to Main](../README.md)