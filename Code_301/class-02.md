# jQuery, Events, and The DOM

---

## jQuery

jQuery is a JavaScript file that we include in our web pages that lets us find elements using CSS-style selectors and then do something with those elements using jQuery methods.

### Find Elements Using CSS-Style Selectors

A function called `jQuery()` lets us find elements and creates an object called **jQuery** to reference those elements. `$()` is often used as a shorthand for `jQuery()`.

**Similarities to DOM**

- jQuery selectors perform a similar task to traditional DOM queries with simpler syntax.
- We can store the `jQuery` object in a variable, just as you can with DOM nodes.
- We can use jQuery methods and properties (like DOM methods and properties) to manipulate the DOM nodes that we select.

The jQuery object has many methods that we can use to work with the elements we select and represent tasks that we commonly need to perform.

### Do Something with the Elements Using jQuery Methods

A `jQuery` object is created by the `jQuery()` function. The object and the elements it contains is referred to as a **matched set** or a **jQuery selection**. Methods of the `jQuery` object to update the elements that it contains.

```JavaScript
$('li .hot').addClass('complete');
```

### Why Use jQuery?

Everything jQuery does can be accomplished with standard JavaScript. It is mostly used because it makes coding simpler. _"Write less, do more"_

1. Simple Selectors
1. Common Tasks in Less Code
1. Cross-Browser Comompatibility

### Matched Sets/jQuery Selections

When we select one or more elements, a jQuery object is returned, known as a _matched set_ or _jquery selection_.

- **Single Element**
  - If a selector returns one element , the jQuery object contains a reference to just one element node. _(each element selected is given an index number. In the case of a single node the index is 0)_.
- **Multiple Elements**

  - if a selector returns several elements, the jQuery object contains references to each element.

  Some jQuery methods both retrieve information from, and update the contents of elements.

- **Get Information**
  - If a jQuery selection holds more than one element, and a method is used to get information from the selected elements, it will retrieve data from only the first element in the matched set.
- **Set Information**
  - If a jQuery selection holds more than one element, and a method is used to update information on the page, it will update ALL of the elements in the matched set, not just the the first one.

When we create a selection with jQuery, it stores a reference to the corresponding nodes in the DOM tree. It does not copy them.

The jQuery object is an array-like object because it stores a list of the elements in the same order that they appear in the HTML document.

Creating a jQuery object takes time, processing resources, and memory because the interpreter must:

1. Find the matching nodes in the DOM tree
1. Create the jQuery object
1. Store references to the nodes in the jQuery object

So, if the code needs to use the same selection more than once, it is better to use that same jQuery object again rather than repeating the process above. To do this we store a reference to the jQuery object in a variable. This is known as Caching.

_When a variable contains a jQuery object, it is often given a name beginning with the **$** symbol (to help differentiate it from other variables)._

### Looping and Chaining

With jQuery, when a selector returns multiple elements, we can update all of them using one method, without needing a loop. This is known as **implicit iteration**.

When we want to get information from a series of elements, we can use the `.each()` method, rather than writing a loop.

The process of placing several methods in the same selector is reffered to as **chaining** and results in far more compact code:

```JavaScript
$('li[id!="one"]').hide().delay(500).fadeIn(1400);
```

However, to make the code easier to read, we can place each new method on a new line:

```JavaScript
$('li[id!="one"]')
.hide()
.delay(500)
.fadeIn(1400);
```

Chaining works on _most_ methods used to **update** the jQuery selection. It _does not_ work on methods that **retrieve** information from the DOM.

### Checking A Page Is Ready

jQuery's `.ready()` method checks that the page is ready for our code to work with:

```JavaScript
$(document).ready(function() {
  // Script goes here
});
```

- `$(document)` creates a jQuery object representing the page
- `.ready()` when the page is ready, the function inside the parentheses is run

the more commonly used shorthand for this is:

```JavaScript
$(function(){
  // Script goes here
});
```

A positive side-effect of writing jQuery code inside this method is that it creates function-level scope for its variables preventing naming collisions with other scripts that might use the same variable names.

### The `load` Event vs. The `.ready()` Method vs. Placing Scripts Before the Closing `</body>` Tag

**The `load` Event**

jQuery's `.load()` method has been replaced by the `.on()` method. It fires after the page and all of its resources have loaded.

We should use this when our script relies on assets to have loaded (i.e. images, etc) to be functional.

**The `.ready()` Method**

jQuery's `.ready()` method checks if the browser supports the `DOMContentLoaded` event and, if it does, creates an event listener that responds to that event, firing as soon as the DOM has loaded.

Using this can make our pages appear as if they are loading faster because it does not wait for other assets to finish loading.

**Placing Scripts Before the Closing `</body>` Tag**

When we place our script at the end of the page, the HTML will have loaded into the DOM before the script runs.

People still use the `.ready()` method so that scripts will still work if someone moves the script tag somewhere else in the HTML page.

### Getting Element Content

The `.html()` and `.text()` methods both retrieve and update the content of elements.

- `.html()` retrieves only the HTML inside the _first_ element in the matched set, along with any of its descendants
- `.text()` returns the content from every element in the jQuery selection, along with the text from any descendants

### Updating Elements

Four methods that update the content of all elements in a jQuery selection:

- `.html()` This method gives every element in the matched set the same new content. The new content may include HTML.

- `.text()` This method gives every element in the matched set the same new text content. _Any markup would be shown as text._

- `.replaceWith()` This method replaces every element in a matched set with new content. It also returns the replaced elements.

- `remove()` This method removes all of the elements in the matched set.

**Using a Function to Update Content**

The following function takes the text from each selected element and places it inside `<em>` tags:

```JavaScript
$('li.hot').html(function() {
  return '<em>' + $(this).text() + '</em>';
});
```

1. `return` indicates that the content should be returned by the function
1. `<em>` tags are placed around the text content of the list item.
1. `this` refers to the current list item. `$(this)` places that element in a new jQuery object so that we can use jQuery methods on it.

## 6 Reasons for Pair Programming

1. **Greater Efficiency** - Though pair programming takes slightly longer, it is proven to produce higher-quality code that requires less troubleshooting later. Therefore, it is more efficient that two people working on separate features. solutions can be reached faster through the sharing of ideas and discussion.
1. **Engaged Collaboration** - When 2 programmers focus on the same code, the experience is more engaging and both programmers are more focused. They rely on each other and can often find solutions together without needing additional help.
1. **Learning From Fellow Students** - because everyone has different approaches to solving problems, pair programming exposed each developer to new solutions to problems. Teammates often have strengths and weaknesses in differing areas. This allows the partner with more experience to teach the partner with less experience about a certain skill. This helps solidify understanding
1. **Social Skills** - Because communication is key in pair programming, practicing it can help develop interpersonal skills. Being able to work well with others is a valuable asset when searching for employment in the field.
1. **Job Interview Readiness** - A common step in many interviews involves pair programming between a current employee and an applicant. This allows companies to see how the prospective employee would fit into their team. Pair programming strengthens these skills.
1. **Work Environment Readiness** - Many companies that utilize pair programming expect to have to train new employees on how they operate. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job.

[Back to Main](../README.md)
