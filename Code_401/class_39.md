# Redux - Additional Topics

## What’s the best practice for “pre-loading” data into the store (on application start) in a Redux application?

The best practice is to utilize React's `useEffect` to dispatch actions to reducers in a "`componentDidMount`" sort of way.

## What’s the best practice for “pre-loading” data into the store (on application start) in a Redux application?

We export the actual async action from our reducer. The ***thunk***, being middleware, lives in its own file and applied in the `index.js` file where the store is created and the reducers are combined.

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **middleware** | *chainable code you can put between the framework receiving a request, and the framework generating a response to accomplish a variety of things or to alter the original request before it resolves in some manner including adding CORS headers, logging, compression, and more.* [Redux](https://redux.js.org/understanding/history-and-design/middleware) |
| **thunk** | *In computer programming, a thunk is a subroutine used to inject an additional calculation into another subroutine. Thunks are primarily used to delay a calculation until its result is needed, or to insert operations at the beginning or end of the other subroutine. `redux-thunk` is the most common async middleware, letting developers write plain functions that may contain async logic.* [Wikipedia](https://en.wikipedia.org/wiki/Thunk) |


[Back to Main](../README.md)