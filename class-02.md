# Introductory HTML and JavaScript
---

## HTML Text
In HTML we add *tags* to the content of the page that provide additional meaning and also help define the appropriate structure for the page. This is known as **markup**.

HTML includes both **structural tags** and **semantic tags**. Structural tags give the content structure within the page, such as whether text should be displayed as a heading or as a paragraph. They can add line breaks or subscript as well.
Semantic tags provide various bits of information about where emphasis should be placed in a sentence or when text is a definition or is an acronym, for example.

### Structural Tags Examples

| **Tag** | **Description** |
| --- | --- |
| `<h1>-<h6>` | Headings size 1 through 6 |
| `<p>` | Paragraph |
| `<b>` | Bold |
| `<i>` | Italics |
| `<sup>` | Superscript |
| `<sub>` | Subscript |
| `<br />` | Line break |
| `<hr />` | Horizontal |

### Semantic Tags Examples

| **Tag** | **Description** |
| --- | --- |
| `<em>` | Shows emphasis of a word or words in text by italicizing them |
| `<strong>` | Indicates a strong importance of the text contained within by showing them in bold |
| `<blockquote>` | Indicates longer quotes, displaying them in indented paragraphs |
| `<q>` | for shorter quotes contain with normal text |
| `<abbr>` | Uses the *title* attribute to expand the abbreviation or acronym |
| `<del>` | Used to show content that has been removed from the page with strikethrough text |
| `<dfn>` | Indicates the defining instance of a new term. *(some browsers put these in italics)* |

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

| **Selector Type** | **Matched Target**                                | **Example**        |
| ----------------- | ------------------------------------------------- | ------------------ |
| _universal_       | all elements on page                              | **\***             |
| _type_ or *element*           | element names                                     | **h1, p, article** |
| _class_           | elements with specified class attribute           | **.class**         |
| _ID_              | elements with specified id attribute              | **\#id**           |
| _descendant_      | elements which are descendants of another element | **li>a**           |

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
