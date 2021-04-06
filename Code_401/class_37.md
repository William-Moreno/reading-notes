# Redux - Combined Reducers

## Why choose Redux instead of the Context API for global state?

In medium and larger scale apps or apps with more complex states, Redux is much easier to implement and optimize.

## What is the purpose of a reducer?

The purpose of a reducer is to receive and interpret actions and then change or update state based on what action was taken.


## What does an action contain?

Actions are objects that contain two components, a type and a payload. The *type* element indicates the type of action being performed. The *payload* component of an action is any information concerning or concerned by the action that is not specifically its type or status.

## Why do we need to copy the state in a reducer?

In Redux, reducers are never allowed to mutate the original or current state values. They can only make copies of the original values and then they can mutate the copies. Reasons for this include:
- It causes bugs
- It can make it harder to understand why or how the state has been updated
- It makes it harder to write tests

[Redux Docs](https://redux.js.org/tutorials/fundamentals/part-3-state-actions-reducers#reducers-and-immutable-updates)


## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **immutable state** | *states which are not allowed to be modified, or mutated, in anyway. Typically, this is achieved by employing  values and pure functions.* |
| **time travel in redux** | *Time travel debugging refers to the ability step forward and backward through the state of you application, empowering the developer understand exactly what is happening at any point in the app’s lifecycle.* [gitconnected](https://levelup.gitconnected.com/build-time-travel-debugging-in-redux-from-scratch-665fea8fc6cc) |
| **action creator** | *a function that returns an action object which would then need to be dispatched.* |
| **reducer** | *a function that determines changes to an application's state. It uses the action it receives to determine this change.* |
| **dispatch** | *this is a function in Redux that triggers and 'action', which is the only way to implement a state change* [react-redux](https://react-redux.js.org/using-react-redux/connect-mapdispatch#:~:text=dispatch%20is%20a%20function%20of,connect%20does%20it%20for%20you.) |


[Back to Main](../README.md)