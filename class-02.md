# Introductory HTML and JavaScript

---

## HTML Text

In HTML we add _tags_ to the content of the page that provide additional meaning and also help define the appropriate structure for the page. This is known as **markup**.

HTML includes both **structural tags** and **semantic tags**. Structural tags give the content structure within the page, such as whether text should be displayed as a heading or as a paragraph. They can add line breaks or subscript as well.
Semantic tags provide various bits of information about where emphasis should be placed in a sentence or when text is a definition or is an acronym, for example.

### Structural Tags Examples

| **Tag**     | **Description**           |
| ----------- | ------------------------- |
| `<h1>-<h6>` | Headings size 1 through 6 |
| `<p>`       | Paragraph                 |
| `<b>`       | Bold                      |
| `<i>`       | Italics                   |
| `<sup>`     | Superscript               |
| `<sub>`     | Subscript                 |
| `<br />`    | Line break                |
| `<hr />`    | Horizontal                |

### Semantic Tags Examples

| **Tag**        | **Description**                                                                       |
| -------------- | ------------------------------------------------------------------------------------- |
| `<em>`         | Shows emphasis of a word or words in text by italicizing them                         |
| `<strong>`     | Indicates a strong importance of the text contained within by showing them in bold    |
| `<blockquote>` | Indicates longer quotes, displaying them in indented paragraphs                       |
| `<q>`          | for shorter quotes contain with normal text                                           |
| `<abbr>`       | Uses the _title_ attribute to expand the abbreviation or acronym                      |
| `<del>`        | Used to show content that has been removed from the page with strikethrough text      |
| `<dfn>`        | Indicates the defining instance of a new term. _(some browsers put these in italics)_ |

## Introducing CSS

CSS treats each HTML element as if it appears inside its own box and then uses rules to indicate how that box, or element, should appear. These rules are structured as follows:

```
h1 {color: red;}
```

_This rule changes to color of 'heading 1' text to red._

- A CSS rule consists of a selector and a declaration. In this case, the selector is `h1` and the declaration within the {} brackets is `color: red;`
- Selectors determine which element or elements the rule applies to.
- Declarations indicate the styling to apply to the selected element. They consist of one or more properties and their desired values.

## Internal CSS versus External CSS

CSS can be internal or external _(sometimes even both)_ to the HTML document. However, the vastly preferred method is external.

- **Internal** - The CSS is written inside `<style>` tags, usually located in the `<head>` of the HTML document. It is typically used in single page websites when it is used.
- **External** - The CSS for the HTML document is located in a separate file. A `<link>` element is added to the HTML document, usually in the `<head>`, to tell the browser where to find the styling file for the webpage. Keeping the CSS in its own file keeps code cleaner and less cluttered. It also makes it easier to style multiple pages of a single site, because each separate HTML document can reference the same CSS file.

## Common CSS Selectors

| **Selector Type**   | **Matched Target**                                | **Example**        |
| ------------------- | ------------------------------------------------- | ------------------ |
| _universal_         | all elements on page                              | **\***             |
| _type_ or _element_ | element names                                     | **h1, p, article** |
| _class_             | elements with specified class attribute           | **.class**         |
| _ID_                | elements with specified id attribute              | **\#id**           |
| _descendant_        | elements which are descendants of another element | **li>a**           |

## CSS Rules Cascade

A hierarcy exists to govern application of conflicting CSS rules for the same targeted element.

- If two selectors are identical the last rule entered will take precedence
- If a selector is more specific than the other, it will take precedence
  - if `!important` is added to the end of a declaration, it will always take precedence

## Inheritance

Some CSS properties are inherited and others are uninherited. Inherited rules apply to the child elements of an element.

- Examples of inherited properties are:

  - font-family
  - color

- Examples of properties which are not inherited are:
  - background-color
  - border properties

## Quirks

Different operating systems and browsers _(especially older or less-used ones)_ can cause your page styling to differ from what you planned. When this happens, it's often called a "CSS Bug" or a "browser quirk".

## Basic JavaScript Instructions

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

### Comments

Comments should be used in certain areas to explain what our code does. There are two ways to denote comments when coding JavaScript: **single line** and **multi line**.

- Single line comments are added to the end of a line and take the form of:

```JavaScript
// comment goes here
```

- Multi line comments tend to span 2 or more complete lines and are defined like this:

```JavaScript
/* first comment line
second comment line
third comment line. */
```

Sometimes these comments can also be used to temporarily "turn off" part of our code while we are writing it, testing it or debugging it...

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

When naming or dealing with variables it is important to remember that JavaScript is a **CASE SENSITIVE** language. A clear and descriptive name should be striven for as well, for the sake of clarity and making our code easier to read.

```
randomNumber !== randomnumber !== RandomNumber !== RANDOMNUMBER !== RaNdOmNuMbEr
```

### The 6 Rules for Naming Variables

1. The name **must** begin with a letter, dollar sign or underscore. Must **not** start with a number.
1. The name can include letters, numbers, dollar signs and underscores. We must **not** use a dash or a period in a variable name.
1. We cannot use **keywords** or **reserved** words.
1. All variables are case-sensitive. While they would be technically separate variables, it is bad practice to create two variable such as _score_ and _Score_.
1. We should use a name that describes the kind of information the variable stores. For instance: _firstName_.
1. When a variable name is made up of multiple words, they should be written in "**camelCase**".

### Arrays, Expressions and Operators

Arrays are special types of variables that store **lists** of related information in a single variable. They are often created with an _array literal_ in the following manner, rather than with an _array constructor_:

```Javascript
var myFamily;
myFamily = ["Laurel","Riley","Alexis"];
```

This is an array with a length of 3. However, since arrays are "0-based" the first position, or **index**, in this array is actually 0 and the last is 2.

Thus, the value of `myFamily[1]` would be `"Riley"`.

Arrays are very helpful when we don't know how many items a list might contain. Values can be added to, removed from and changed in an array. Changing a value already in an array is done with a command like:

```JavaScript
myFamily[0] = "Lolo";
```

### Expressions & Operators

**Expressions** rely on things called **operators** and result in a single value and basically come in two types:

- Expressions that assign a value to a variable:
  - `var color = 'beige';`
- Expressions that use two or more values to return a single value:
  - `var area = 3 * 2;`

There are 5 types of operators that allow us to create single values from single or multiple values. They are:

| **Operator** | **Description**                                                                                                            | **Example**                   |
| ------------ | -------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| Assignment   | `=` This assigns a value to a variable                                                                                     | `color = 'beige';`            |
| Arithmetic   | These perform basic math. For example `+` , `-` , `*` , etc                                                                | `area = 3 * 2;`               |
| String       | `+` is the **only** string operator and allows us to combine strings                                                       | `greeting = 'Hi ' + 'Molly';` |
| Comparison   | These compare two values and returns a _Boolean_ value, either **true** or **false**. Examples are `>` , `===` , `!=`, etc | `buy = 3 > 5;`                |
| Logical      | These combine expressions and, again, return a Boolean value. These include operators such as `&&` _(and)_ and `!` _(not)_ | buy = (5 > 3) && (2 < 4);`    |

## Decisions & Loops

_Conditional_ statements allow our code to make decisions about which code to execute next. To do this, it utilizes comparison operators such as (`===` , `!==` , `<` , `>=` , _etc._) to compare two operands. Logical operators allow us to combine more than one set of comparison operators using logical operators (`&&` , `||` , `!`).

Comparison operators return single values of `true` or `false`. Logical operators allow us to compare the results of more than one comparison operator.

### Short-Circuit Evaluation

Logical operations are evaluated left to right. If the first operation provides enough information to answer the evaluation, there is no need to evaluate the second or subsequent conditions.

- Logical AND (`&&`)
  - **false** and anything - the evaluation cannot possibly be true.
- Logical OR (`||`)
  - **true** and anything - the evaluation cannot possibly be false.

`if` statements allow us to execute a block of code only if a condition is true or skip past the block to the next line of code if the condition is false.

Example:

```JavaScript
if (score >= 50) {
  congratulate();
}
```

`if ... else` statements allow us to execute one set of code if a condition is true and a different set if the condition is false.

Example:

```JavaScript
if (score >= 50) {
  congratulate();
}
else {
  encourage();
}
```

## Git Commit Messages

Teams should agree on a commit message convention in order to create a useful revision history. This convention should address:

- **style** - Markup syntax, wrap margins, grammar, capitalization and punctuation to help remove guesswork.
- **Content** - What info should a commit message contain and what should it _not_ contain.
- **Metadata** - How should tracking IDs, pull request numbers, etc. be referenced?

### 7 Rules of a Great Git Commit Message...

1. Separate subject from body with a blank line
1. Limit subject line to 50 characters
1. Capitalize subject line
1. Do not end the subject line with a period
1. Use the imperative mood in the subject line _(Subject should complete the sentence "If applied, this commit will..." and make sense.)_
1. Wrap the body at 72 characters
1. Use body to explain what and why, not how

[Back to Main](README.md)
