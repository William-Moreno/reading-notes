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

**Imperative Approach**

- We create a new empty array
- We iterate over the existing array
- We push the desired elements into the new empty array, filling it

**Declarative Approach**

Using a first-class entity function and a higher-order function like `.filter` we can accomplish the same results. Often this can be done in less code and has more modularity built into it.

- We create a simple evaluation function like:
```JavaScript
function larger(integer) {
  return integer < this;
}
```
- We then pass that function into the higher-order `.filter` function as an argument:
```JavaScript
function sortArray(x, numberArray) {
  return numberArray.filter(larger, x);
}
```

*(In this case, `this` will be the second parameter of the `.filter` function)*

### Map

These same concepts can be applied to maps. A map applies a function to all of the elements of an array and transforms it into an array of new values.

**Imperative Approach**

- We create a new empty array
- We iterate over the existing array
- We push the transformed elements into the new empty array, filling it

**Declarative Approach**

- We create a simple function to construct sentences:
```JavaScript
const generateSentence = (pet) => `${pet.name} is a good ${pet.type}!`;
```
- We then pass that function as an argument into the higher-order `.map` function:
```JavaScript
const petSentences = (pets) => pets.map(generateSentence);
```

*(`Math` functions/methods could also be passed into these higher-order functions rather than used in for... loops for instance)*

These same priciples can be applied to the `.reduce` higher-order function just as easily.

## Refactoring for Performance abd Readability

In his article [***"Refactoring JavaScript for Performance and Readability (with Examples!)"***](https://dev.to/healeycodes/refactoring-javascript-for-performance-and-readability-with-examples-1hec), Andrew Healey says that *good code* lives in the middle ground between speed and comprehendability.

In the two examples of this article, Healey shows and explains some minor changes to improve the overall code:

In one example, an array of ever-growing length was being iterated over with a for loop to find a specific element and also to check if the element existed in any of the arrays indices. The refactor was to change the array of things into a map of things instead and to assign keys to each element as it was added/generated. The for loop was then replaced with a short if statement to throw an error if a searched item was not in the map. To determine an items existence and to locate the data within now required the program to look in one specific place for the data insted of checking every index of a large array.

### Strategies

While there are no absolutes when it comes to clean code, there are some straightforward methods we could implement:

- Return early from functions
- Cache variables so functions can be read like sentences
- Check for Web APIs before implementing our own functionality

***Because of the low value placed on refactoring by many businesses today, it is IMPORTANT to get our code right the first time.***




[Back to Main](../README.md)