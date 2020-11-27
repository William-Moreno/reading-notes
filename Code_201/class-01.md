# Introductory HTML and JavaScript

---

## How People Access the Web

Most people access websites using software called **web browsers**.

- Firefox
- Internet Explorer
- Safari
- Chrome
- Opera

Some people who are visually impaired use programs called **screen readers** to access websites. These programs read out the contents of a computer screen to the user.

People access websites on an increasing number of devices including, but not limited to:

- desktop computers
- laptops
- tablets
- mobile phones

### Web Servers

Web servers are specialized computers that host websites. They are optimized to send out web pages and are constantly connected to the internet. They are most commonly maintained by **web hosting** companies.

## Websites

All websites use **HTML** _(HyperText Markup Language)_ and **CSS** _(Cascading Style Sheets)_. Many websites also incorporate **JavaScript** to give them functionality or make them dynamic. Content management systems, blogging software and e-commerce platforms routinely make use of additional elements/technologies in their websites.

All websites have a unique **IP address** associated with them and the server they are located on. **Domain Name System** (DNS) servers are repositories for all of these addresses and they function similarly to phone book listings to direct browsers to the correct location of the website..

## Structure

HTML is the language which describes and gives web pages structure. It is made up of characters called HTML **elements** inside of angled brackets called **tags**. These usually come in pairs: an opening and a closing tag. Each element tells the browser something about the structure of the information contained within. Tags act like containers for the text or other information located inside of them.

```HTML
<h1>This would be a heading</h1>
```

would indicate to the browser to display:

# This would be a heading

on the web page.

`<h1>` is the **opening tag**

`</h1>` is the **closing tag**

Most elements can have one or more **attributes** such as _class_ or _id_ which provide additional information about their contents. Attributes consist of two parts: a **name** and a **value** separated by an `=` sign. for instance:

```HTML
<p lang="en-us">Paragraph in English</p>
```

### Basic HTML Structure of a Web Page

```HTML
<!DOCTYPE html>
  <html>
    <head>
      <title>The Title of the Page</title>
    </head>
    <body>
      <h1>A Heading in the Body of the Page</h1>
      <p>Anything in the body is displayed in the main browser window</p>
    </body>
  </html>
```

- `<body>` Everything inside this element is shown in the main browser window.
- `<head>` Located before the `<body>` element, this element contains information _about_ the page.
- `<title>` The content of this element is displayed at the top of the browser or on the 'tab' above the address bar. The `<title>` element is usually located within the `<head>` element of the page.

- `<!DOCTYPE html>` Each webpage should begin with a declaration such as this, which tells the browser the version of HTML the page is using.

##### To learn HTML, you need to know what tags are available for you to use, what they do, and where they can go.

## Extra Markup

- DOCTYPES tell browsers which version of HTML is being used
- Comments can be added to code to make it easier to understand. They are not displayed on the web page and are structured as follows:

```HTML
<-- Comment Here -->
```

- The **id** and **class** attributes are used to identify or group specific elements
- `<div>` and `<span>` elements allow us to group block-level and inline elements together, respectively
- `<iframes>` allow other web pages to be shown through windows "cut out"" of the web page
- The `<meta>` tag is an **open tag** located in the `<head>` tag and contains information about the web page. It is not visible to users but can convey information about the page to search engines, who created the page, or if the page is time-sensitive
- **Escape characters** are used to include special characters in web pages. Some examples are:

| **Character** | **CODE**   | **Description**        |
| ------------- | ---------- | ---------------------- |
| &lt;          | `&lt;`     | _Less-than sign_       |
| &gt;          | `&gt;`     | _Greater-than sign_    |
| &amp;         | `&amp;`    | _Ampersand_            |
| &quot;        | `&quot;`   | _Quotation Mark_       |
| &copy;        | `&copy;`   | _Copyright symbol_     |
| &reg;         | `&reg;`    | _Registered trademark_ |
| &trade;       | `&trade;`  | _Trademark_            |
| &divide;      | `&divide;` | _Division sign_        |

## HTML5 Layout

HTML5 introduced a new set of elements that help define the stucture of a web page. Where traditional layouts typically consisted of multiple `<div>` elements, the use of these new _semantic_ tags or elements provides clearer code. They also work better with screen readers utilized by users with visual impairments. `<div>` is still used, but not nearly as much now.

The new HTML5 elemanets indicate the purpose of different parts of a web page and help to describe its structure. Examples are:

- `<header>` Header. Appears at the top of pages and sometimes even the top of an `<article>` or `<section>` within the page.
- `<footer>` Footer. Appears at the bottom of pages and sometimes even the bottom of an `<article>` or `<section>` within the page.
- `<nav>` Navigation. Typically used for primary site navigation.
- `<article>` Article. A container for any section of the page that could feasibly stand alone. There may be several on any given page.
- `<aside>` Aside. A container for content related to the entire page. Alternatively, if it is located within an article container, it contains content related to that article.
- `<section>` Section. Groups related content together and commonly has its own heading.

## Process & Design

When creating a new web page, it is important to understand who our target audience is. _Why will they come to our site? What information are the looking for? How often are they likely to return?_

Popular design tools used in the planning websites are **site mapping** and **wireframing**.

- Site maps allow us to plan the structure of a website
- Wireframes allow us to organize the information that needs to go on a page

_Design is about communication._ **Visual hierarchy** helps users understand what we are trying to tell them. We can differentiate between separate information using **size**, **color** and **styling**. **Grouping** and **similarity** can help simplify the information we present.

## JavaScript

JavaScript can make our web pages more interactive. It does this in four ways:

- **Access Content** - JavaScript can be used to select can be used to select any element, attribute or text from our HTML page
- **Modify Content** JavaScript can add or remove elements, attributes and text to or from the page.
- **Program Rules** JavaScript can specify a series of steps for a browser to follow which allows it to access or change the content of the page.
- **React to Events** JavaScript can dictate that a specifc script should run when a particular event occurs. _(ie. when a button is pressed)_

Using JavaScript we can implement things such as slideshows, forms, filtering data or reload parts of the web page.

## JavaScript: Key Concepts in Computer Programming

1. What is a script and how do we create one?
1. How do computers fit in with the world around them?
1. How do we write a script for a web page?

### What is a script and how do we create one?

- A script is a series of instructions that the computer can follow to achieve a specific goal.
- When a script runs, it may only use a subset of all of the instructions it contains.
- Computers approach tasks differently than humans. Our instructions must allow the computer to solve the task programmatically.
- When writing a script, we must break down our goal into a sequence of tasks and then work out each step needed to complete each individual task. _(flowcharts are helpful planning these)_

## How do computers fit in with the world around them?

- Computers create models of the world using data.
- These models use objects to represent physical things. Objects can have:
  - **Properties** that tell us about the object
  - **Methods** that perform tasks using the properties of the object
  - **Events** which are triggered when a user interacts with the computer
- As programmers, we can write code to say "When this event occurs, run that code."
- Web browsers create a model of the web page using HTML. Each HTML element creats it own **node** _(a kind of object)_.
- We write code that uses the browser's model of our web page in order to make the page interactive.

## How do we write a script for a web page?

- It is best to keep JavaScript code separate in its own JavaScript file.
- JavaScript files are text files, but they have the `.js` extension.
- The `<script>` tag in an HTML page tells the browser to load the JavaScript file. _(this is similar to the relationship between the `<link>` tag and a CSS file.)_
- While the JavaScript code we write may alter the original web page, it does not change any of the code in the HTML file.

[Back to Main](../README.md)
