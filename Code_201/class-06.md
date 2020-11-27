# Problem Domain, Objects and the DOM

---

## Understanding Problem Domains

Many problem domains we face as programmers are difficult to understand. Often, these problem domains also look completely different depending on individual viewpoints.

Programmers are also routinely not given complete information about the problem domain, whihch leads to the issue of not even having the information needed to understand it.

## Programming Is Easy If You Understand...

When the problem domain is understood, dlear and concise, writing the code becomes far easier.

> Understanding is the most critical piece...

Coversely, it is difficult to solve a problem before you know what the question is.

## What can we do?

We can do one of two things:

1. Make the Problem Domain easier, simpler, less complex, etc.
   - The domain can sometimes be made easier by cutting out cases and narrowing focus to a smaller piece of the problem.
1. Get better at understanding Problem Domains.
   - We can become better at understanding problem domains, and avoid rushing to start coding before we thoroughly understand enough of the problem domain.

It may take a little more time and money to invest in understanding, but it cost significantly more to have to do things over rather than get them right the first time.

## JavaScript Objects

**Objects** group together a set of variables and functions to create a model of something. In an object, variables and functions take on new names. In an object:

- _variables_ become known as _properties_. Properties tell us about the object. The value of a property can be a string, number, Boolean, array, or even another object.
- _functions_ become known as _methods_. Methods represent tasks that are associated with the object. The value of a method is always a function.
- Properties and methods have a name and a value. The name is called a **key**.
- An object cannot have two keys with the same name, because keys are used to access their corresponding values.

In JavaScript:

- Variables have a name and an assigned value of a string, number or Boolean.
- Arrays have a name and a group of values. _(Each item in an array is a name/value pair because it has an index and a value.)_
- Named functions have a name and value that is made up of a set of statements to run when the function is called.
- Objects consist of a set of name/value pairs, but the names are referred to as keys.

### Creating an Object: Literal Notation

Literal notation is the easiest and most popular way to creat objects. The object is the set of keys and values inside a set of curly braces. It is stored in a variable.

```JavaScript
var hotel = {
   name: 'Quay',
   rooms: 40,
   booked: 25,
   checkAvailability: function() {
      return this.rooms - this.booked;
   }
};
```

When creating an object:

- Separate each key from its value with a colon.
- Separate each property and method with a comma. (But not after the final value)
- In the `checkAvailability()` method above, the **this** keyword is used to indicate that it is using the _rooms_ and _booked_ properties of **_this_** object.
- Treat values for properties like we would for variables, strings live in cuotes and arrays line in square brackets.

### Accessing an Object and 'Dot Notation'

We can access the properties or methods of an object using dot notation. We can also access properties using square brackets. To access properties of methods of objects, we use the name of the object followed by a period and then the name of the property or method we want to access. This is called **dot notation**. The period is known as the **member operator**.

```JavaScript
var hotelName = hotel.name;
```

We can also access the properties or methods using square bracket syntax.

```JavaScript
var hotelName = hotel['name'];
```

This notation is most commonly used when:

1. THe name of the property or method contains special characters
1. The name of the property is a number (technically allowed, but should be avoided).
1. A variable is being used in place of the property name

Functions that are used as methods of an object can still have parameters. When called as methods, arguments are passed to the method just like when we call a regular function.

## Document Object Model

The **D**ocument **O**bject **M**odel *(DOM)*specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser. It is neither part of HTML, nor part of JavaScript, but rather a separate set of rules. These rules cover two primary areas:

1. Making a model of the HTML page. Using the **DOM Tree** model the DOM specifies the way in which the browser should construct the model out of object components.
1. Accessing and changing the HTML page. THe DOM defines methods and properties to access and update the various objects within its model. This updates what is displayed in the actual browser. The DOM is often called an **Application Programming Interface** or (**API**). Through this, set the rules for what our script can ask the browser about the current model/page, and what it can tell the browser to update on that model/page.

### The DOM Tree

As a page loads, the browser creates a **DOM Tree** model of that page which it stores in its memory. These models consist of four main types of **nodes**. Each node is an object with properties and methods. Scripts access and update the DOM tree and make changes to only the DOM tree whcih are then reflected in the browser. The source HTML file remains unaltered. The four types of nodes are:

- **The Document Node** - This node is always at the top of the tree and represents the entire page. It is the starting point for all visits to the DOM tree. Every element, attribute and piece of text in the HTML is represented by its own individual **DOM Node**.
- **Element Nodes** Each HTML element describes part of the structure of the HTML page, from headings to paragraphs of text. To access the DOM tree, we start by looking for elements. Once we have accessed them, we can access their text and attribute nodes. Relationships between the document and all of the element nodes are described using the terminology of a family tree: parents, children, siblings, etc. _(Every node is a descendant of the document node)_.
- **Attribute Nodes** - Opening tags of HTML elements can carry attributes which are represented by attribute nodes in the DOM tree. These nodes are _not_ children of the elements. Once an element is accessed, we can use methods and properties to read or change that element's attributes.
- **Text Nodes** - Once we have access to an element node, we can then reach the text nodes within that element. Text nodes cannot have _children_. A text node is always a new branch of the DOM tree and no further branches come off of it.

### Working with the DOM Tree (2 - Steps)

1. Locate the node that represents the element we want to work with.
1. Use its text content, child elements and attributes.

#### Step 1: Access the Elements

An overview of the two types of methods and properties that access elements, **DOM Queries** and **traversing the DOM**:

- Select an Individual Element Node
  - Three common ways to select individual elements:
    1. `getElementById()` - Usesthe value on an element's `id` attribute
    1. `querySelector()` - Uses a CSS selector, and returns the first matching element
    1. Traversing Between Element Nodes
       - `parentNode` - Selects the parent of the current element node
       - `previousSibling` / `nextSibling` - selects the previous or next sibling from the DOM tree
       - `firstChild` / `lastChild` - Selects the first or last child of the current element
- Selecting Multiple Elements _(Nodelists)_
  - Three common ways to select multiple elements:
    - `getElementsByClassName()` - Selects all elements that have the specified value for their class attribute
    - `getElementsByTagName()` - Selects all elements that have the specified tag name
    - `querySelectorAll()` - Uses a CSS selector to select all matching elements

#### Step 2: Working with Those Elements

When people say the DOM is working with an element, it is actually working with the node that represents that element. Sample methods and properties that work with the elements:

- Access/Update text nodes
  - `nodeValue` - This property lets us access or update contents of a text node..
- Work with HTML Content
  - `innerHTML` - A propetry that allows access to child elements and text content
  - `textContent` - A property that allows access to only the text content
  - Several methods which allow us to create, remove, or add nodes to a tree _(known as DOM manipulation)_
    - `createElement()`
    - `createTextNode()`
    - `appendChild()`
    - `removeChild()`
- Access or Update Attribute Values
  - `className` / `id` - (properties) Lets us get or update the value of these attributes
  - `hasAttribute()` - (method) Checks if an attribute exists
  - `getAttribute()` - (method) Gets the value of an attribute
  - `setAttribute()` - (method) Updates the value
  - `removeAttribute()` - (method) removes the attribute

### Caching DOM Queries

Methods that find elements in the DOM a DOM queries. When we need to work with an element more than once, we should _cache_ the reference location of the element in a variable:

```JavaScript
var itemOne - getElementById('one');
```

### Accessing Elements

DOM queries can return a single element or a NodeList, which is a group of elements. These node lists are collections of nodes and they are similar to arrays in that they are 0-indexed lists.

#### Methods that Return a Single Element Node

- `getElementById('id')` - selects an individual element given the value of its id attribute.
- `querySelector('css selector')` - uses CSS selector syntax that would select one or more elements. This method returns _only the first_ of the matching elements.

#### Methods that Return One or More Elements as a Nodelist

- `getElementsByClassName('class')` - selects one or more elements given the value of their class attribute. **_This method is faster than `querySelectorAll()`._**
- `getElementsByTagName('tagName')` - selects all elements on the page with the specified tag name. **_This method is faster than `querySelectorAll()`._**
- `querySelectorAll('css selector')` - uses CSS selector syntax to select one or more elements and returns all of those that match.

### Selecting Individual Elements

`getElementById()` and `querySelector()` both use similar syntax and search an entire document and return individual elements. `getElementById()` is the quickest and most efficient way to access an element. `querySelector()` is very flexible because its parameter is a css selector and therefore it can target many more elements.

```JavaScript
document.getElementById('one')
```

`document` refers to the document object, which must be accessed in order to access elements.

`.` is the member operator - "dot notation".

`getElementById()` is the method being employed.

`'one'` is the parameter of the method.

### NodeLists

NodeLists look like arrays and are number like arrays, but they are not actually arrays. They are a type of object called a **collection**.
Properties and methods exist for NodeLists, notably:

- `length` list the number of items in the NodeList
- `item()` returns a specific node from the Nodelist when we supply the index number of the item we want. It is not uncommon to use square-bracket array notation when retrieving these items from the list however.

Example DOM queries that return NodeLists:

- `getElementsByTagName()`
- `getElementsByClassName()`
- `querySelectorAll()`

### Selecting Elements from NodeLists

There are two ways to select an element from a NodeList: The `item()` method and array syntax. Both require the index number of the desired element. Array syntax is preferred over the `item()` method however because it is faster. Store the NodeList in a variable if it will be repeatedly used.

```JavaScript
var elements = document.getElementsByClassName('hot');
if (elements.length >= 1) {
   var firstItem = elements[0];
}
```

1. a NodeList containing elements with a class value of hot is created and stored in a variable called elements
1. if there are at least one values in the NodeList, run the code in the `if` statement
1. get the first element from the NodeList ([0])

### Repeating Actions for an Entire NodeList

We can loop through each node in a NodeList and apply the same statements to each. For instance the following gathers all list items with a class attribute of 'hot' and changes them to 'cool'.

```JavaScript
var hotItems - document.querySelectorAll('li.hot');
for (var i = 0; i < hotItems.length; i++) {
   hotItems[i].className = 'cool';
}
```

### Traversing the DOM

Five properties can be used on an element to select another element with respect to the current element. This is known as traversing the DOM.

1. `parentNode`
1. `previousSibling`
1. `nextSibling`
1. `firstChild`
1. `lastChild`

### Adding and Removing HTML Content

There are two different approaches to adding and removing content from a DOM tree. the `innerHTML` property and DOM manipulation. There are security risks associated with `innerHTML` but is is faster and better suited to updating entire fragments. DOM manipulation can be safer, but it requires more code and can be slower by comparison, but it easily targets individual nodes in the DOM.

#### `innerHTML` Property

`innerHTML` can be used on any element node to either retrieve or replace content. The content is provided as a string and can include markup.

1. Create a variable holding the markup
1. Select the element whose content you want to update
1. Update content of selected element with the new markup

#### DOM Manipulation Methods

DOM manipulation refers to a set of methods that allow us to create element and text nodes and then attach them to or remove them from the DOM tree.

1. Create new text node
1. Create new element node
1. Add text node to element node
1. Select element you want to ad the new fragment to
1. Append the new fragment to the selected element

### Three Techniques for Adding HTML to a Web Page.

`document.write()`

- Advantage
  - Quick, easy way to show beginners how content can be added to a page
- Disadvantages
  - It only works when the page initially loads
  - If you use it after the page loads it can:
    1. Overwrite the whole page
    1. Not add the content to the page
    1. Create a new page
  - It can cause problems with XHTML pages that are strictly validated
  - This method is very rarely used by programmers and is generally frowned upon

`element.innerHTML`

- Advantages
  - Can use it to add a lot of new markup using less code than DOM manipulation methods
  - It is faster than DOM manipulation when adding a lot of content
  - It is a simple way to remove all of the content from an element _(using a blank string)_
- Disadvantages
  - Should not be used to add content that has come from a user due to potential security risks
  - Can be difficult to isolate single elements within a larger DOM fragment
  - Event handlers may no longer work as intended

_DOM Manipulation_

- Advantages
  - Suited to changing a single element from a DOM fragment where there are many siblings
  - It does not affect event handlers
  - Easily allows a script to add elements incrementally
- Disadvantages
  - It is slower than `innerHTML` when a lot of changes to content must be made
  - More code must be written to achieve the same results as `innerHTML`

### Attribute Nodes

Once we have an element node, we can us other properties and methods to access and alter its attributes. _For instance_:

```JavaScript
document.getElementById('one').getAttribute('class');
```

Sample methods than can be used to manipulate these values:

| **Method/Property** | **Description**                                      |
| ------------------- | ---------------------------------------------------- |
| `getAttribute()`    | gets the value of the attribute                      |
| `hasAttribute()`    | checks if the element node has a specified attribute |
| `setAttribute()`    | sets the value of an attribute                       |
| `removeAttribute()` | removes an attribute from an element node            |
| `className`         | gets or sets the value of the `class` attribute      |
| `id`                | gets or sets the value of the `id` attribute         |

[Back to Main](../README.md)
