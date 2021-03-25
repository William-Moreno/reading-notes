# Routing

## Do child components have direct access to props/state from the parent?

Props, states and callback functions can be passed down to children from parents. However, the only way for children to be able to pass states back up to a parent is through the use of the passed down callback functions.


## When a component “wraps” another component, how does the child component’s output get rendered?

The "wrapped" component is rendered within the bounds of the rendering of the "wrapping" component.

## Can a component, such as `<Content />`, which is a child also be used as a standalone component elsewhere in the application?

I do not believe so. All of the components of a React application are children of other components. All components are descendants in some way of the App.js/Index.js file.

## What trick can a parent use to share all props with it’s children

 I have found that I can simply pass `this.state` to children and that conveys most if not all props to the child. I have also heard that it can be done with a spread operator.


## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **props.children** | *Essentially, props.children is a special prop, automatically passed to every component, that can be used to render the content included between the opening and closing tags when invoking a component.* [codeburst.io](https://codeburst.io/a-complete-guide-to-props-children-in-react-c315fab74e7c) |
| **composition** | *In React, apps are built of components. Composition is the arrangement of these components and the flow of data between them.* |


[Back to Main](../README.md)