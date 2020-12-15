# Components
---
## EJS Partials

**Partials** are like functions we can call to populate parts of web pages with the same content. We define these chunks of resuable code in a separate file and then include that file whenever we need it. Partials are also native to EJS, as opposed to layouts, which requires an additional package to be installed before use.

Partials can be used to pre-construct common or repeatable portions/pieces of multiple web pages in a website. Primary candidates for this methodology might be headers, navbars, footers and the like.

### Creation and Definition

To create these partials, we create a *partials* directory inside our *views* directory. Then we create a `.ejs` file or files in that new directory, usually named to describe what the partial will generate, *i.e. header.ejs*. In these files we define the HTML for that piece or feature. For example, a re-usable `footer.ejs` file might be defined like this:

```html
<footer class="footer">
  <p>Code Fellows Copyright 2020</p>
</footer>
```

### Usage

Once they are defined, our partials are ready for use. We always use the delimiters `<%` and `%>` to surround JavaScript or non-HTML syntax when using EJS. To include a partial, for instance the same footer, we simply insert the following code into our .ejs page:

```html
<%- include(partials/footer') %>
```

In this manner, we only need write the code for the footer once and we can then easily insert it into any number of .ejs pages using a single line of code. We can even insert multiple partials in a single or several pages.

[Back to Main](../README.md)