# Operators and Loops

---

## Operators

Two types of operators are **comparison** operators and **logical** operators. Comparison operators evaluate a situation and return **Boolean** values of either _true_ or _false_.

### Comparison Operators

- `==` - _is equal to_
- `!=` - _is NOT equal to_
- `===` - _strict equal to_
- `!==` - _strict NOT equal to_
- `>` - _greater than_
- `<` - _less than_
- `>=` - _greater than or equal to_
- `<=` - _less than or equal to_

Logical operators compare the results of more than one comparison operator, also returning a Boolean value.

### Logical Operators

- `&&` - _Logical AND_
- `||` - _Logical OR_
- `!` - _Logical NOT_

## Loops

Loops are programming tools that check for a condition and run a specified block of code if the condition returns **true**. After executing the block of code, the loop checks the condition again and continues to repeat the block of code intil a check returns **false**. Then the loop is exited.

There are three common types of loops:

- **for** - used when we need to run the code a specific number of times. In a for loop, the condition is typically a "counter".
- **while** - used when we don't know how many times the code should run. The condition can be something other than a counter.
- **do while** - similar in all respects to the **while** loop save for one key difference. The **do while** loop will always execute its code at least once.

### For Loop Counters

The for lopp uses a counter as a condition to instruct the code to run a specified number of times. The counter of a for loop consists of three parts: **initialization**, **condition** and **update** and is contained in the parenthesis following the for keyword. Here is an example of a for loop set up:

```javascript
for (var i = 0; i < 10; i++) {
  // Code goes here
}
```

- `var i = 0` - _initialization_ the variable i is created only one time when the for loop is first run.
- `i < 10` - _condition_ the loop should continue to run until it reaches the specified number.
- `i++` - _update_ every time the loop completes the block of code it increments the counter.

[Back to Main](../README.md)
