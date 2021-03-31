# Context API

## Describe use cases for `useMemo()` and `useReducer()`

`useMemo()` should be used to avoid unnecessary and costly calls to repeatedly run a funtion on every render. This is because it memoizes output of a function. After calling the the function once, there is no need to call it again until the function's dependencies change in some way. `useMemo()` Should only be used in areas where our code already works without it. It should be used to optimize.

[Digital Ocean](https://www.digitalocean.com/community/tutorials/react-usememo)

`useReducer()` is preferred over `useState()` when we have complex state logic or instances when state changes are progressive. It works well with the following examnple situations:
- JavaScript objects or arrays as state
- complex state transitions
- differing but intertwining properties that should be managed in one state object

[*"useReducer vs useState in React"*](https://www.robinwieruch.de/react-usereducer-vs-usestate)


## Why do custom hooks need the use prefix?

The name of any custom hook should begin with `use`. This convention indicates to developers that hooks are used within the file/custom hook.

## What do custom hooks usually do?

They allow the creation of modular functionality, usable across multiple components, with the advantage of being able to 'hook' into the React API for things like state and component lifecycle.

## Using any list of custom hooks, research and name one that you think will be useful in your applications

This is a toss-up for me between `useFormState` and `constate`. I really like the simplicity of useFormState, and I am sure I will use it at some point, but being able to use constate to share state across components definitely sounds good to me.

## Describe how a hook that fetches API data might work

The hook might take in a url, a method, and a body. Using axios or something similar, useState and possibly useEffect, an API call can be made based on and using the parameters passed in and then an objects state could be 'set' based on the results of the API call.

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **reducer** | *manages state in an application. A reducer is a function which takes two arguments -- the current state and an action -- and returns based on both arguments a new state.* [*"What is a Reducer in JavaScript/React/Redux?"*](https://www.robinwieruch.de/javascript-reducer) |


[Back to Main](../README.md)