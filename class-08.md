# More CSS Layout

---

## Overlapping and Floating Elements

The boxes of elements that appear later in the HTML code can sometimes overlap the ones which came before. We can control which elements sit on top by utilizing the `z-index` property. Sometimes known as the **stacking context** manipulation of this property is tantamount to "bringing to the front" and "sending to back".

The float property allows us to take an element in normal flow and place it as far to the left or right of the containing element as possible. Other elements that reside in the same container will flow around the floated element. When we use the `float` property, we should also use the `width` property to indicate how wide the floated element should be.

`float` is often used to place elements side-by-side, but can have unexpected results when neighboring elements have differing heights. This can be solved by using the `clear` property.

The `clear` property allows us to indicate that no element in the same container should touch the left, right or both sides of a box.

## Screen Sizes

Different visitors to web sites will have different sized screens that show differing amounts of information. Our design must, therefore be able to work on a range of different sized screens. Also, some devices have a higher resolution than desktop computers and most operating systems allow users to adjust the resolution of their screens.

## Pages Sizes

Because screen sizes and display resolutions vary so much, web designers often try to create pages around 960-1000 pixels wide.

### Fixed Width Layouts

Fixed width layout designs do not change size as the user increases or decreases the size of their browser window.

- Advantages
  - Pixel values are accurate at controlling size and positioning of elements.
  - The designer has far greater control over the appearance and position of items on the page than with _liquid_ layouts.
  - You can control the lengths of lines of text regarless of the size of the user's window.
  - The size of an image will always remain the same relative to the rest of the page.
- Disadvantages
  - You can end up with big gaps around the edge of a page.
  - If the user's screen is a much higher resolution than the designer's screen, the page can look smaller and text can be harder to read.
  - If a user increases font size, text might not fit into the alotted spaces.
  - The design works best on devices that have a site or resolution similar to that of desktop or laptop computers.
  - The page will often take up more vertical space than a liquid layout with the same content.

### Liquid Layouts

Liquid layout designs stretch and contract as the user increases or decreases the size of their browser window. They typically use percentages.

- Advantages
  - Pages expand to fill the entire browser window so there are no spaces around the page on a large screen.
  - If the user has a small window, the page can contract to fit it without the user having to scroll to the side.
  - The design is tolerant of users setting font sizes larger than the designer intended _(because the page can stretch)_.
- Disadvantages
  - If you do not control the width of sections of the page then the design can look very different than you intended, with unexpected gaps around certain elements or items squashed together.
  - If the user has a wide window, lines of text can become very long, which makes them harder to read.
  - If the user has a very narrow window, words may be squashed and you can end up with few words on each line.
  - If a fixed width item _(such as an image)_ is in a box that is too small to hold it _(because the user has made the window smaller)_ the image can overflow over the text.

## Layout Grids

Many web designers use a grid structure to help them position items on a page. Grids set consistent proportions and spacing between itemsto create a professional looking design. One widely used layout tool is called the **960 pixel grid**. It is possible to create many different layouts using this one versatile grid. Far from being restricting, a grid:

- can create a continuity between different pages which may use different designs.
- helps users predict where to find information on various pages.
- makes it easier to add new content to the site in a consistent manner.
- helps people collaborate on the design of a site in a consistent way.

A wide range of layouts can be created from a single 960 pixel wide 12 column grid, for example. Each column in a grid has a margin setting. This setting creates a gap between the columns that is twice as wide as the setting.

### CSS Frameworks

CSS frameworks aim to make our life easier by providing the code for common tasks:

- Creating layout grids
- Styling forms
- Creating printer-friendly versions of pages
- and more...

We can include the CSS framework code in our projects rather than writing the CSS from sctratch.

- Advantages
  -They save us from repeatedly writing code for the same tasks
  - They will have been tested accross different browser versions
- Disadvantages
  - They often require that we use class names in our HTML code that only control the presentation of the page _(rather than describe content)_
    -In order to satisfy a wide variety of needs, they often contain more code than we need for our particular web page _(bloat)_

#### The 960.GS CSS Framework & Grid

One of the most popular uses of CSS frameworks is in creating grids to layout pages. There are several grid frameworks available, but one of the most popular is the [_960 Grid System_](www.960.gs). It provides a style sheet we can include in our HTML pages by linking to it. Then, all we have to do is provide the appropriate classes to our HTML code and it will create multiple column layout for us.

- link to the 960_12_col.css stylesheet in the `<head>` of the page
- create a `<div>` to contain the entire page and give it a class of `"container_12"` to indicate that we will be using a 12 column grid
- we also provide that `<div>` a class of `clearfix` to ensure that browsers know the height of the containing box, because it only contains floated elements

### Multiple Style Sheets

Multiple CSS files can be included in one page. Some authors split their CSS style rules into separate style sheets: one to control the layout and another to control fonts and colors, etc. Some authors subdivde their style sheets roles into even smaller scopes, in a more **modular** approach.

There are two ways in which we can add multiple style sheets to our page:

1. Our HTML page can link to a single style sheet and that stylesheet can use the `@import` rule to import other style sheets.
   - If a stylesheet uses the `@import` rule, it should appear before the other rules.
1. We can use a separate `<link>` element for each style sheet in our HTML.
   - As with all style sheets, if two rules apply to the same element, then the rules that appear later in the document will take precedence over previous rules. So the order in which we link to the style sheets should be considered.

[Back to Main](README.md)
