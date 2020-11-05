# Forms and Events

---

## Forms

> The best known _form_ on the web is probably the search box that sits right in the middle of Google's homepage.

Forms are used for many other things besides conducting a search, however. Some of them are:

- registering for memberships
- shopping online
- signing up for newsletters and mailing lists

There are several types of form controls that you can use to collect information from site visitors:

- Adding Text
  - **Text Input _(single-line)_** - Used for a single line of text such as an email address or name
  - **Password Input** - Like a single line text box, but it masks the characters entered
  - **Text Area _(multi-lines)_** - For longer text entries like messages or comments
- Making Choices
  - **Radio Buttons** - For use when a user must select one of a number of options
  - **Checkboxes** - When a user can select and unselect one or more options
  - **Drop-down Boxes** - When a user must pick one of a number of options from a list
- Submitting Forms
  - **Submit Buttons** - To submit data from your form to another web page
  - **Image Buttons** - Similar to submit buttons but they allow you to use an image
- Uploading Files
  - **File Upload** - Allows users to upload files to a website

### How Forms Work

A User fills in a form and then presses a button to submit the information to the server. The name of each form control is sent to the server along with the value the user entered. The server processes the information using a programming language. THe server creates a new page to send back to the browser based on the information received.

A form may have several form controls. The server needs to know which piece of inputted data corresponds with which form element. For example:

```HTML
username=Ivy
```

### Form Structure

We create forms in HTML with the `<form>` element. This tag always carries an `action` attribute (which is the url of the page that will receive the information from the form) and a `method`, which will be either `"get"` or `"post"`. by default this value is "get".

#### Text Input

We create this with the `<input>` element with the attributes - `type="text"`, `name`, and `maxlength `

#### Password Input

This is similar to above, however, our `<input>` can have `type="password"` instead

#### Text Area

Created with `<textarea>`

#### Radio Button

`<input>` with `type="radio"` can have `name`, `value` and `checked` attributes _("checked" can cause a choice to be already selected when the page loads)_

#### Checkbox

`<input>` with `type="checkbox"` can have `name`, `value` and `checked` attributes _(the same as radio button)_

#### Drop Down List Box

The `<select>` element is used to create a drop down
list box containing two or more `<option>` elements. the `<name>` attribute indicates the form control being sent to the server

#### Multiple Select Box

The `<select>` element can turn a drop down box into a mutli-selection tool using the `<size>` and `<multiple>` attributes

#### File Input Box

Here we use `<input>` with a `type="file"`. It will display a text input bar with a browse button at the far end. The `method` attibute of the `<form>` element must be set to a value of `post` in order to allow the user to upload files

#### Submit Button

Use a `type="submit"` with `<input>` to create a submit button. Optionally, it can have a `name` or `value` _(which controls the text on the button)_ attribute associated with it

#### Image Button

If we want to use an image when creating the submit button, `type="image"` is the only difference between the two

### HTML5 Form Validation

Traditionally, form validation has been performed using JavaScript. But HTML 5 is introducing validation which is now performed by the browser instead.

- Reduces the amount of work the server has to do
- Enables users to see if there are problems with the form faster than if validation were performed on the server

HTML5 add more `types` for the `<input>` element including:

- `"date"`
- `"email"`
- `"url"`
- `"search"`

It also allows us to use `placeholder` to display default text in the box until the user clicks it.

## CSS Lists, Tables & Forms

In addition to the CSS properties covered in other chapters which work with the contents of all elements, there are several others that are specifically used to control the appearance of lists, tables and forms.

### List Properties

- `list-style-type` allows us to control the shape or style of the bullet point or numeber of list items
- `list-style-image` allows us to specify an image that we supply a url path to, to use in place of a bullet point
- `list-style-position` allows us to designate whether we want the marker inside or outside the container holding the list items

There is also a `list-style` shorthand to apply any combination of these properties in a single line.

### Table Properties

Many of the properties we already use are utilized to style a table:

- `width` to set the width of the table
- `padding` to set the space between the border of each table cell and its content
- `text-transform` to convert the content of the table headers to uppercase
- `letter-spacing`, `font-size to add additional styling to the content of the table headers
- `border-top`, `border-bottom` to set borders above and below the table headers
- `text-align` to align the writing to the left or right of table cells
- `background-color` to change the background color of alternating rows of the table
- `:hover` to highlight a table row when a user mouses over it

In addition to those these properties are also useful:

- `empty-cells` lets us determine if a cell with no value will disply its borders
- `border-spacing` and `border-collapse` manage the gaps, or lack thereof, between cells.

### Styling Forms

When it comes to forms, there do not appear to be any tailor made properties for styling them. Rather, we must make use of many other CSS properties by applying them to the form element in intelligent manners, similar to the list shown for tables, above.

When styling forms, we should strive to align controls vertically using CSS, because this makes them easier to use.

## JavaScript Events

Events are the browser's way of indicating when something has happened _(a page is loaded, a button has been clicked)._ There are a lot of events that occur while we are browsing the web. Any of them can be used as a trigger to activate a function in our JavaScript code. A few examples are:

- UI Events
  - `load`
  - `error`
  - `scroll`
- Keyboard Events
  - `keypress`
  - `keydown`
- Mouse Events
  - `click`
  - `mouseover`
- Focus Events
  - `blur`
- Form Events
  - `input`
  - `submit`
  - `copy`
- Mutation Events
  - `DOMNodeInserted`
  - `DOMNodeRemovedFromDocument`

When the user interacts with the HTML on a web page, three steps are involved in getting JavaScript code to trigger. Collectively, these steps are known as **event handling**

1. Select the **element** node(s) we want the script to respond to.
1. Indicate which **event** on the selected node(s) will trigger the response.
1. State the **code** we want to execute when the event occurs.

Event handlers let us indicate which event we are waiting for on any particular element. There are three types of event handlers:

- HTML event handlers
  - This is **bad** practice, but it still exists in older code
- Traditional DOM event handlers
  - **Event handlers** were introduced in the original specification for the DOM and are considered better than HTML event handlers because they let us separate the JavaScript from the HTML
- DOM level 2 event handlers

  - **Event listeners** were introduced in an update to the DOM specification and are now considered the favored way of handling events

  #### Traditional DOM Event Handlers

  All modern browsers understand this way of creating an event handler, but we can only attach one function to each event handler.

  ```JavaScript
  element.onevent = functionName;
  ```

  #### Event Listeners

  Event listeners are a more recent approach to handling events. They can deal with more than one function at a time but they are not supported in older browsers.

  ```JavaScript
  element.addEventListener('event', functionName [, Boolean]);
  ```

  Because we cannot have parenthesis after the function names in event handlers or listeners, passing arguments requires a workaround. This can be done by wrapping the function call inside an **anonymous function**.

### Event Flow and Why Flow Matters

HTML elements nest inside other elements. If you hover or click on a link, you will also be hovering or clicking on its parent elements. The flow of events only really matters when our code has event handlers on an element _and_ one of its ancestor or descendant elements.

#### The Event Object

When an event occurs, the event object tells us information about the event, and the element it happened upon.

#### Event Delegation

Creating event listeners for a lot of elements can slow down a page, but event flow allows us to listen for an event on a parent element. Thus, we can use event delegation to monitor for events that happen on all of the children of an element.

[Back to Main](README.md)
