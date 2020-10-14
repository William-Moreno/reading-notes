# Structuring webpages with HTML

## Process

When designing a successful website several things must be considered:

- **Target audience** - this includes things such as: age, gender, where they live, types of devices they use to browse and more.
- **Why people visit the site** - what goals or motivations bring people to the site? Reasearch? Shopping? Services?
- **What information visitors need** - knowing what goals bring visitor's to the site can help you predict what type of information you should provide.
- **How often people will visit the site** - depending on the role of the site, it may need to be updated more often. Sometimes this may affect only parts of an entire site.

## Design

Several strategies exist for designing websites. One possible progression is:

- **site mapping** - using cards representing different bits of information and arranging them in an order, grouping similar bits.
- **wireframe** - creating a black and white diagram of the webpage on paper or a whiteboard sketching in the size and layout of various elements. No colors, fonts or images should utilized here. Focus should stay on layout.
- **visual design** - using concepts such as visual hierarchy, grouping and similarity to organize and prioritize information.
- **Navigation** - navigation elements should be clear, contextual, concise and consistent.

## HTML5 Layout Elements

Prior to HTML5, web page authors mostly used `<div>` elements when creating all of the different sections of web page. HTML5 brings semantic tags into use which indicate the kind of content you will find in them. These work better with readers as well. _Examples of these are:_

- `<header>` - header of either the page , or sometimes articles or sections within
- `<footer>` - footer of either the page , or sometimes articles or sections within
- `<nav>` - navigation
- `<article>` - a section of the page that could stand alone
- `<aside>` - contains content related to the entire page
- `<section>` - groups related content together

## Extra Markup

**Comments** - Used to add a comment to your code that will not display in the browser. `<!-- comment-->`

**ID Attribute** - Every HTML element can carry an id attribute to uniquely identify it. The value should start with a letter or underscore and must be unique. _Added to the opening tag._ `id="value"`

**Class Attribute** - Every HTML element can carry an class attribute to identify it, often as part of a group of elements. Several elements can carry the same class attribute. _Added to the opening tag._ `class="value"`

## Block & Inline Elements

Some elements will always appear in blocks and others will appear "inline". There are also ways to group text and elements in a manner to appear either as blocks or inline.

### Block Element Examples

- `<h1>`
- `<p>`
- `<ul>`
- `<li>`

  - The `<div>` element allows the grouping of a set of elements together into one block-level box.

### Block Element Examples

- `<a>`
- `<b>`
- `<em>`
- `<img>`

  - The `<span>` element is the inline equivalent of the `<div>`.

[Back to Main](README.md)
