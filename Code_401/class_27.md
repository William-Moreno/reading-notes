# Props and State

## Does a Deployed React Application Require a Server?

You don’t necessarily need a static server in order to run a Create React App project in production. It also works well when integrated into an existing server side app. 

- [Create React App Docs](https://create-react-app.dev/docs/deployment/)

## Why Do We Prefer to Test a React Application at the Behavior Rather Than the Unit Level?

Unit testing React components that have purely presentational concerns is fairly stright-forward. But, testing more complex React components that are responsible for behavior is just as important. These include components that:
- maintain internal state
- leverage lifecycle methods
- have side effects like:
  - `setTimeout()`
  - `setInterval()`

-[medium](https://medium.com/capital-one-tech/unit-testing-behavior-of-react-components-with-test-driven-development-ae15b03a3689)

## What Does `npm run build` Do?

Builds the app for production to the `build` folder.
It correctly bundles React in production mode and optimizes the build for the best performance.

## Describe the Actual Composition / Architecture of a React Application

In React applications, components are the UI building blocks. They are analogous to pure functions in function composition. In React composition model is a sort of tree made up of components. Within this 'tree' there exist rules such as:

- A parent may or may not know what the children are ahead of time
- Children do not know their parents
- Children do not know their siblings

The components have well-defined interfaces, called ***'props'***, that allow explicit interactions between them.
- [*"React is All About Composition"*](https://medium.com/leanjs/react-is-all-about-composition-f9f49dec183c#:~:text=Composition%20is%20the%20act%20of,building%20blocks%20of%20function%20composition.)


## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **BDD** | *Behavior-Driven Development. An Agile software development process that encourages collaboration among developers to formalize a shared understanding of how the application should behave.* [Wikipedia](https://en.wikipedia.org/wiki/Behavior-driven_development) |
| **Acceptance Tests** | *Formal testing with respect to user needs, requirements, and business processes conducted to determine whether a system satisfies the acceptance criteria and to enable the user, customers or other authorized entity to determine whether to accept the system.* [Wikipedia](https://en.wikipedia.org/wiki/Acceptance_testing) |
| **mounting** | *The process by which React adds nodes to the DOM. (removing them from the DOM is known as "unmounting")* [Stack Overflow](https://stackoverflow.com/questions/31556450/what-is-mounting-in-react-js) |
| **build** | *When a user visits a site, each of the files will require an additional HTTP request, making the site slower to load. To remedy this, we can create a “build” of the app, which merges all CSS files into one file, and does the same with JavaScript.* [Stack Overflow](https://stackoverflow.com/questions/43830866/what-is-npm-run-build-in-create-react-app/48614507#:~:text=When%20a%20user%20visits%20your,the%20same%20with%20your%20JavaScript.) |