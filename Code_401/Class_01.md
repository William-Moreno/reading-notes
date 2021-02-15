# Node Ecosystem, TDD, CI/CD

## `Array.map()`

In `Array.map()`, `.map()` is a method that creates and returns a new array. The new array is populated by values obtained by executing a designated callback function on each element of the original array in turn. A simple example might be:

```JavaScript
const arr = [1, 2, 3];
const andOne = arr.map((element) => element+= 1);

console.log(andOne);
```
The displayed result will be the array [2, 3, 4] because the callback function added 1 to each value in the original array before inserting it into the new array.

## `Array.reduce()`

In `Array.reduce()`, `.reduce()` is a method used to "reduce" the array it is used on to a single value. The value does not have to be a number. It could be a string or a boolean for example. The value is obtained by executing a callback function on each element of the array and tracking the returned value in the accumulator argument for the next iteration. After the final iteration, this accumulator becomes the final single value. The initial value of the accumulator can be designated, but if it is not the first element of the array will be used as the inital accumulator and skipped. Here is an example:

```JavaScript
const arr = [81, 3, 9];
const reducer = arr.reduce((accum, value) => accum / value);

console.log(reducer);
```

The displayed result will be 3. Since we did not designate an initial value for accum, it became the first element of the array, 81. The callback function then divides accum by the current value (81 / 3) and assigns the value 27 to accum for the next and final iteration. This time when the callback function divides accum by the current value (27 / 9) the result of 3 is assigned to accum. As this is the final iteration, the value returned from the `arr.reduce()` is 3.

