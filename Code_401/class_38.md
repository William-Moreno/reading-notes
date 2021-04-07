# Redux - Combined Reducers

## How granular should your reducers be?

This often depends on the logic behind the update to state. If the hadling of all of the parts is more-or-less the same they can be completed by a general action. However, if the differing pieces require different types of handling by multiple reducers, deicated actions which update only those parts of state are usually preferred.

## Pro or Con – multiple reducers can “fire” when a commonly named action is dispatched

It is suggested that we write independent small reducer functions that are each responsible for updates to a specific slice of state, a practice called “reducer composition”. A given action can be handled by all, some, or none of them. The components remain decoupled from the actual data changes, as one action may affect different parts of the state tree, and there is no need for the component to be aware of this. 

- [Redux FAQ](https://redux.js.org/faq/actions)

## Name a strategy for preventing the above

Redux's middleware makes it possible to intercept dispatched actions and add additional complex behavior around them, including side effects. Redux suggests that code with side effects should be part of the action creation process. While that logic can be performed inside of a UI component, it generally makes sense to extract that logic into a reusable function so that the same logic can be called from multiple places—in other words, an action creator function. The simplest and most common way to do this is to add the Redux Thunk middleware that lets you write action creators with more complex and asynchronous logic. 

- [Redux FAQ](https://redux.js.org/faq/actions)


## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **store** | *In Redux, this is the location of the state tree for the application. State within this structure can only be modified through the use of dispatches and reducers.* |
| **combined reducers** | *A helper function converts an object populated by differing reducing functions into a single reducing function which can be passed to `createStore`.* [Redux API Reference](https://redux.js.org/faq/actions) |


[Back to Main](../README.md)