# Component Composition

## Can a Parent Component Access the State of a Child Component?

A child's state can be accessed using *'Refs'*. These Refs are assigned in the parent component for the child component. Following this assignment, the child's state becomes accessible using the *'current'* attribute of the ref.

- [GeeksforGeeks](https://www.geeksforgeeks.org/how-to-access-childs-state-in-react/)

## What Can Be Passed Along in a Prop Variable?

Props can be used to pass along data to React components much like arguments are passed to functions. These props *(properties)* can be string, integers, objects, even functions, or styling information. In most basic terms, props convey data or information of some type to a child component.

## How Can a Child Component *"Know"* the State of Another Component?

React components cannot access the state of other components, becuase state is private to each component. There ***are*** ways to pass or change state from other components in specific ways. We can pass a component's state to its child components as props. Components that share a parent can both access the same state in a similar fashion. Changing the state of another component can be accomplished by passing callback functions as props from a parent component to a child component. When the functions are called by the child, they alter the state of the parent component.

- [Codecademy](https://discuss.codecademy.com/t/can-a-component-access-the-state-of-another-component/394157)

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **component props** | *Props are arbitrary inputs that can be used to pass along data to React components much like arguments are passed to functions.* |
| **component state** | *Component state is specific to a particular component and can only be updated within that component. Component state can also be passed down to its children components via props.* |
| **application state** | *Application state is global. Typically it is held in a library and any component within the application is able to access it if they are connected to that "library".* |

## 3 Things I Had Previously Heard of and Now Have Better Clarity On

1. The React component lifecycle and how it works at a high level
1. Props can even transport React components
1. `setState` is asynchronous, which can be mitigated by passing it functions to ensure updates to **state** occur in a desired sequence

## 3 Things I Am Hoping to Learn More About in the Upcoming Lecture

1. High Order Components- what they are and how they do what they do
1. How to use `props.children` as well as a practical example of it in action
1. More about mocking API communications in tests

## I Am Most Excited About Trying to Implement or See How These Work:

- Trying out the Mock Service Worker library in an attempt to write better tests for my applications

[Back to Main](../README.md)