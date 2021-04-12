# React Native

## Compare and Contrast Redux Toolkit with Redux “Ducks”

Both toolkit and ducks deal with Redux actions. reducers and stores. Their differences are mostly in the structuring of the files. Ducks are what the reducer/action files are called in basic Redux. In Redux ToolKit, the files that fill the same function as the 'ducks' are called slices. Slices tend to be more compact and streamlined than duck files, and basically consist of an object that contains the name of the slice of state, the initial state of the slice's contents and the reducers with the action/logic included. Ducks ten to be larger files that contain the initial state of contents, then defines the reducer and it's associated actions and typically then defines functions that dispatch those actions. Both ducks and the toolkit favor a feature-first approach to file structure as well as modularity.

## What is the principle advantage of Redux Toolkit

 It allows us to write more efficient code, speed up the development process, and automatically apply the best-recommended practices.
 - [GeeksforGeeks](https://www.geeksforgeeks.org/what-is-redux-toolkit-and-why-it-is-more-preferred)

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **redux toolkit slices** | *A Redux Slice is a collection of reducer logic and actions for a single feature of our app. It represents a fragment of our app's state.* [medium.com](https://medium.com/swlh/redux-in-react-js-reducers-and-slices-bafafec781e3) |
| **namespace** | *a method of defining redux action type constants wherein the name of the constant is simple and clear and the value is essentially namespaced to ensure the action is only associated with a particular slice of state* |


[Back to Main](../README.md)