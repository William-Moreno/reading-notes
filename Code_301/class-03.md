# Mustache.js and Flexbox

---

## JavaScript Templating

JavaScript templating is a fast and efficient way to render client-side view templates with JavaScript, using a JSON data source. The template engine replaces variables and instances declared in the template file with actual values at runtime, and converts the template into an HTML file sent to the client.

### Mustache

**Mustache** is a logic-less template syntax. It can be used for HTML, config files, source code - anything. It works by expanding tags in a template using values provided in a has or object.

It is referred to as **"logic-less"** because there are no _ifs_, _elses_ or _for loops_, only **tags**.

**_mustache.js_** is an implementation of the mustache template system in JavaScript. It is considered the base for JavaScript templating and it supports various languages. Which means that we don't need a separate system on the server side.

```JavaScript
Mustache.render("Hello, {{name}}", { name: "Sherlynn" });
// returns: Hello, Sherlynn
```

### Mustache-Express

If we intend to use mustache with Node and Express, we can use **_mustache-express_**. It lets us use Mustache and Express together easily.

1. Configure mustache-express in our server.js/app.js/index.js file
1. Create a views folder and add some html view templates (e.g. hello.html)
1. In the router configuration, use **res.render(TEMPLATE_NAME, JSON_DATA)**

## Flexbox

**Parent Properties**

- `display` defines a flex container; inline or block depending on the given value.
- `flex-direction` establishes the main-axis, thus defining the direction flex items are placed in the flex container.
- `flex-wrap` by default, flex items will all try to fit on one line.
- `flex-flow` shorthand for the `flex-direction` and `flex-wrap` properties.
- `justify-content` defines the alignment along the main axis and helps distribute extra free space leftover.
- `align-items` defines the default behavior for how flex items are laid out along the **cross axis** on the current line.
- `align-content` aligns a flex container's lines within when there is extra space in the cross-axis.

**Children Properties**

- `order` controls the order flex items are laid out in.
- `flex-grow` defines the ability for a flex item to grow if necessary.
- `flex-shrink` defines the ability for a flex item to shrink if necessary.
- `flex-basis` defines the default size of an element before the remaining space is distributed.
- `flex` is the shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined. _It is recommended to use this shorthand property rather than set the individual properties._
- `align-self` allows the default alignment to be overridden for individual flex items.

[Back to Main](../README.md)
