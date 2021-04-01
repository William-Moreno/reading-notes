# `<Login />` and `<Auth />`

## Why is the Context API useful?

The Context API is useful because it allows us to persist and pass data up and down our component tree. We can achieve this without the need to pass props downstream.

## Can a component outside of a provider get its context?

No. To receive context from a provider, a child/component must be one of that provider's context consumers.

## What are some common use cases for using the Context API?

Based on our class discussion yesterday, I would say these would include:
  - authentication/authorization unctions
  - user settings
  - themes for the page

## Describe “Context Hell”

According to [Charles Stover](https://charles-stover.medium.com/you-may-not-need-a-global-god-state-in-react-206930033895#), ***"Context hell"*** is the layer of countless contexts wrapping our React application when we utilize the context API.

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **global state** | *a state and the function to update it which is available to all children components of the app and resides in a context file. *  |
| **global context** | *the sharing of global states across components of the app without the need to explicitly pass *'props'* down the tree.*  |
| **provider** | *accepts a value prop to be passed to consuming components that are descendants of this Provider.* [React Docs](https://reactjs.org/docs/context.html#contextprovider) |
| **consumer** | *descendants of a Provider will re-render whenever the Provider’s value prop changes.* [React Docs](https://reactjs.org/docs/context.html#contextprovider) |


[Back to Main](../README.md)