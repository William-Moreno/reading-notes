# Hooks API

## Why do we not need more `.html` pages in a multi-page React app?

We no longer need multiple `.html` pages in our application because with React, we have access to client-side routing libraries which can emulate having several pages by changing what is displayed to our single page and what isn't, based on a *'route'* being added to the end of the URL in the browser address bar, or by using *'links'* to simulate traversing to a new page.

## If we wanted a component to show up on every page, where would we put it and why?

  - *"Inside the `<BrowserRouter />`, outside a `<Route />`"*, and *"Outside the `<BrowserRouter/>`"*

  Children/components associated with a specific route are placed within `<Route />` tags to display only when THAT route is 'called/hit'. `<Route />`s must live within a `<BrowserRouter />` *(whether it is located in the same file or a parent file)*. However, all components which live outside of specified `<Route />`s, BUT inside those `<BrowserRoutes />`s, will display to all *pages* displayed by their 'sibling' components. Components which are placed outside of `<BrowserRouter />`s, will likely display on all pages as well, since a `<BrowserRouter />` is only required to govern the existence and behavior of its `<Route />` children and descendants, and not required to display components or content.

## What does `props.children` contain?

`props.children` is a special prop that is automatically passed to every rendering component, and consists of all of the components and data/information *(boolean, numbers, strings, functions, even other React components) located between the opening and closing tags designated.

## Vocabulary Terms

| **Vocabulary Term** | **Definition** |
| --- | --- |
| **Composition** | *In React, apps are built of components. Composition is the arrangement of these components and the flow of data between them.* |
| **Children / Child Components** | *JSX components which are nested within a parent React component* |
| **Hash Routing** | *Routing that uses the hash *'#'* portion of the URL to keep our UI synced with our URL. An example might be: `<HashRouter basename="/calendar"/>` `<Link to="/today"/>  renders <a href="#/calendar/today">`* [React Router](https://reactrouter.com/web/api/Link) |
| **Link Routing** | *Provides declarative, accessible navagation around our application and typically looks like this: `<Link to="/about">About</Link>`* [React Router](https://reactrouter.com/web/api/Link) |


[Back to Main](../README.md)