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

Everything jQuery does can be accomplished with standard JavaScript. It is mostly used because it makes coding simpler. *"Write less, do more"*

1. Simple Selectors
1. Common Tasks in Less Code
1. Cross-Browser Comompatibility

### Matched Sets/jQuery Selections

When we select one or more elements, a jQuery object is returned, known as a *matched set* or *jquery selection*.

- **Single Element**
  - If a selector returns one element , the jQuery object contains a reference to just one element node. *(each element selected is given an index number. In the case of a single node the index is 0)*.
- **Multiple Elements**
  - if a selector returns several elements, the jQuery object contains references to each element.

  Some jQuery methods both retrieve information from, and update the contents of elements.

- **Get Information**
  - If a jQuery selection holds more than one element, and a method is used to get information from the selected elements, it will retrieve data from only the first element in the matched set.
- **Set Information**
  - if a jQuery selection holds more than one element, and a method is used to update information on the page, it will update ALL of the elements in the matched set, not just the the first one.


## 6 Reasons for Pair Programming

1. **Greater Efficiency** - Though pair programming takes slightly longer, it is proven to produce higher-quality code that requires less troubleshooting later. Therefore, it is more efficient that two people working on separate features. solutions can be reached faster through the sharing of ideas and discussion.
1. **Engaged Collaboration** - When 2 programmers focus on the same code, the experience is more engaging and both programmers are more focused. They rely on each other and can often find solutions together without needing additional help.
1. **Learning From Fellow Students** - because everyone has different approaches to solving problems, pair programming exposed each developer to new solutions to problems. Teammates often have strengths and weaknesses in differing areas. This allows the partner with more experience to teach the partner with less experience about a certain skill. This helps solidify understanding
1. **Social Skills** - Because communication is key in pair programming, practicing it can help develop interpersonal skills. Being able to work well with others is a valuable asset when searching for employment in the field.
1. **Job Interview Readiness** - A common step in many interviews involves pair programming between a current employee and an applicant. This allows companies to see how the prospective employee would fit into their team. Pair programming strengthens these skills.
1. **Work Environment Readiness** - Many companies that utilize pair programming expect to have to train new employees on how they operate. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job.

[Back to Main](../README.md)