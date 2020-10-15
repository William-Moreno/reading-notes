# Making Webpages Dynamic

---

## JavaScript is the tool that gives webpages functionality; makes them dynamic.

If a webpage were thought of as a house. **HTML** would be the structure of that house, consisting of many elements (_walls, windows, doors, floors, ceilings, rooms, etc_). On the other hand, **CSS** would be the interior (and maybe exterior) decorating of the house (_colors of rugs and walls, styles of windows and doors, furnishings and appliances_). And, in our analogy, **JavaScript** would be the piece responsible for all the functioning features in the house (_wiring, electricity, waterlines, and gaslines_).

#### Three Separate Layers

- **HTML** - Content
- **CSS** - Presentation
- **JavaScript** - Behavior

All three of these layers work together to produce a webpage or website. However, the three layers should be kept in different files, with HTML retrieving information from the other two. This speeds up load times and in the event that the user's browser can not or will not run JavaScript the page will still work.

## JavaScript and HTML

JavaScript is a powerful language whose strength tends to lie in front end development. JavaScript can both retrieve information from the HTML document as well as devliver information to it. JavaScript can even add code to the HTML document without ammending the HTML file. To utilize JavaScript a script tag is entered in the HTML designating the JavaScript file name:

```
<script src="app.js"></script>
```

This tag is usually entered into the HTML just before the closing body tag `</body>`. JavaScript can be written 'inline' within the HTML document and made to function, but it is not best practice.

## The Language

JavaScript consists of a series of instructions, known as **statements**, which the computer follows

**one**

**by**

**one**.

Each statement should start on a new line and end with a semicolon `;`. This make the code easy to read and easy to follow. The semicolon signals the end of a step to JavaScript. Statements can be grouped together or organized into **code blocks** when place between or within curly braces `{ }`.
An example of a statement would be:

```
document.write('Good evening!');
```

- document is an **object**
- write() is a **method** of the _document_ object
- 'Good evening!' is a **parameter** of the _write()_ method

_The . in the statement is known as the_ **member operator**.

## Variables

JavaScript uses **variables** to store bits of data temporarily for use in the script. The are like _short-term_ memory for the program. The value of variables can change each time the script is run. Variables come in several varieties as well. A few values that can be assigned to them are:

- **Numbers** - numbers
- **Strings** - a series of characters or letters between quotation marks
- **Booleans** - true or false

If you are unsure of what kind of data a variable is assigned with the `typeof('variable')` command can tell you.

To be used a variable should be declared. For example:

```
var unknown;
```

The variable is then ready to be assigned a value:

```
unknown = 5;
```

The = sign in this statement is known as an **assignment operator**. Until the variable is assigned a value, its value will be _undefined_.

When naming or dealing with variables it is important to remember that JavaScript is a **CASE SENSITIVE** language.

```
randomNumber !== randomnumber !== RandomNumber !== RANDOMNUMBER !== RaNdOmNuMbEr
```
